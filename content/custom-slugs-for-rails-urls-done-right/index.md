---
title: "Custom slugs for Rails URLs done right"
description: "I’ve seen a lot of examples of this online, and it took a while for me to get it right, so I decided to document it."
date: "2017-07-14T22:21:04.933Z"
categories: []
published: true
canonical_link: https://medium.com/@gilani/using-custom-slugs-for-rails-urls-500eb3f58f3c
redirect_from:
  - /using-custom-slugs-for-rails-urls-500eb3f58f3c
---

I’ve seen a lot of examples of this online, and it took a while for me to get it right, so I decided to document it.

The two cases I’ve used this for:

1.  Vanity URLs, e.g. trying to open a user’s profile at `/u/amingilani`
2.  Obfuscated URLs, e.g. trying to make the [URL](https://hackernoon.com/tagged/url) difficult to guess such as`/transactions/601585f7–0f4a-41e8-bd04-b2eb24262fb4`

Both cases differ only by the fact that the slug is randomly generated in the latter.

Quick definitions:

-   `Slug`: part of the URL to identify the record
-   `Primary key`: a unique identifier for database records
-   `UUID`: Universal unique identifier, a 128 bit generated identifier that depending on the implementation is either guaranteed or is very likely to be unique.

Overview:

1.  We’ll add a unique `slug` column to our database table
2.  We’ll generate a unique slug on creation (only for the 2nd use-case)
3.  We’ll use the slugs in URLs

#### Adding a `slug` column to our database

We’ll need to ensure that our slug is unique, and always present. You can name it “username” or anything more semantic if it’s meant to be part of the model.

```
class AddSlugToRecommendations < ActiveRecord::Migration[5.1]
  def change
    add_column :transactions, :slug, :string, null: false
    add_index :transactions, :slug, unique: true
  end
end
```

#### Generating a unique slug on creation

We’ll use the `securerandom` library that ships with rails to generate a unique UUID. If the UUID (by whatever sorcery) already exists, a new one will be generated instead.

This is only important, if we’re trying to obfuscate our URLS. Ignore this step if you’re letting users set something like `username`

```
class Transaction < ApplicationRecord
  before_create :set_slug

  private

  def set_slug
    loop do
      self.slug = SecureRandom.uuid
      break unless Transaction.where(slug: slug).exists?
    end
  end
end
```

#### Use the slug in URLS

This will have to be set in multiple places:

1.  use the `:slug` param in routes
2.  lookup records using the `:slug` param
3.  Override the `Model#to_param` method to return the`slug` attribute instead of `id`

Tell your routes to use the slug param:

```
Rails.application.routes.draw do
  resources :transactions, param: :slug
end
```

Now your routes will look like this:

```
edit_transaction GET    /transactions/:slug/edit(.:format)
     transaction GET    /transactions/:slug(.:format)
                 PATCH  /transactions/:slug(.:format)
                 PUT    /transactions/:slug(.:format)
                 DELETE /transactions/:slug(.:format)
```

For your controller to lookup records by the slug, stop using the `id` and use the `slug` param instead:

```
class TransactionsController < ApplicationController
  before_action :set_transaction, only: [:show, :edit, :destroy]

  private

  def set_transaction
    @transaction = Transaction.find_by slug: params[:slug]
  end
end
```

Let’s override the `Model#to_param` method so that `form_for @transaction` works:

```
class Transaction < ApplicationRecord
...
  def to_param
    slug
  end
...
end
```

#### Why my way is the best

Unless you’re creating a distributed application with distributed database nodes that need a collision free method to generate primary keys, you don’t need randomly generated ids. You’re just looking for a quick and easy way to hack [URLS](https://hackernoon.com/tagged/urls), which is why this method is awesome.

Using a string as a primary key is significantly slower than an integer during lookups, so every `Model#children` call will be slower.

Using a slug for URL lookups means the slow performance will be limited to URL lookups, which is what you wanted in the first place.
