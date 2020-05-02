---
title: "Semantic UI in Rails via Webpack"
description: "Semantic UI is my favorite UI library when I begin an application, and I use Ruby on Rails for almost all my web applications. With the…"
date: "2020-05-02T22:47:28.855Z"
categories: []
published: false
---

Semantic UI is my favorite UI library when I begin an application, and I use Ruby on Rails for almost all my web applications. With the introduction of Yarn in Rails 5.1, we can use NPM packages directly inside Rails, so stop loading Semantic UI through a CDN (or rails-assets.org) and get it straight from NPM.

#### Installing Semantic UI

Run this:

```
yarn add semantic-ui 
```

Oh wait, did that not work? For the first time in your life did the magical powers of `yarn add` fail you? Yeah, it’s happened to a lot of [people](https://github.com/yarnpkg/yarn/issues/976).

Normally this would work but Semantic UI is designed to be installed via `npm` and built on installation with Gulp interactively. This is what you get when you run it via `npm` :

```
[07:27:38] Starting 'run setup'...
? Set-up Semantic UI (Use arrow keys)
❯ Automatic (Use default locations and all components)
  Express (Set components and output folder)
  Custom (Customize all src/dist values)
```

Thankfully Semantic UI has an auto install, but it requires a bit of a hack. Add a `semantic.json` file to the root of your project:

```
{
  "base": "node_modules/semantic-ui/",
  "paths": {
    "source": {
      "config": "src/theme.config",
      "definitions": "src/definitions/",
      "site": "src/site/",
      "themes": "src/themes/"
    },
    "output": {
      "packaged": "dist/",
      "uncompressed": "dist/components/",
      "compressed": "dist/components/",
      "themes": "dist/themes/"
    },
    "clean": "dist/"
  },
  "permission": false,
  "autoInstall": true,
  "rtl": false,
  "version": "2.3.1"
}
```

Please be sure to replace `version` with whatever version of Semantic UI is the latest. This nifty files tells Semantic to auto install inside a `dist/` directory of the `semantic-ui` folder in `node_modules` 

After you’ve added the file, run `yarn add semantic-ui` again, and it’ll work.

#### Configuring jQuery with Webpack

Semantic UI needs jQuery (oh shut up, I can hear you mentally sighing. It’s not that big a deal), so let’s first install it with:

```
yarn add jquery
```

No surprise there. Now, like any other jQuery extension, Semantic UI’s JavaScript component expects a global `jQuery` object, which we can’t have since we’re using Webpack, but we can trick Semantic UI into thinking it exists by creating a [Webpack Provider](https://webpack.js.org/plugins/provide-plugin/) plugin
