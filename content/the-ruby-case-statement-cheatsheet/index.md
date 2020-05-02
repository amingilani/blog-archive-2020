---
title: "The Ruby Case Statement Cheatsheet"
description: "The Ruby case statement is simple enough to master:"
date: "2018-08-07T05:50:26.798Z"
categories: []
published: true
canonical_link: https://medium.com/@gilani/the-ruby-case-statement-cheatsheet-92275639a398
redirect_from:
  - /the-ruby-case-statement-cheatsheet-92275639a398
---

The Ruby `case` statement is simple enough to master:

```
case a
when 'A', 'B'
  puts 'A or B'
when 'C'
  puts 'A or B'
else
  puts 'Not A, B, or C'
end
```

When using regex (via [documentation](https://devdocs.io/ruby~2.5/syntax/control_expressions_rdoc#label-case+Expression)):

```
case "12345"
when /^1/
  puts "the string starts with one"
else
  puts "I don't know what the string starts with"
end
```

When you want to create more complex statements (via [documentation](https://devdocs.io/ruby~2.5/syntax/control_expressions_rdoc#label-case+Expression)):

```
a = 2

case
when a == 1, a == 2
  puts "a is one or two"
when a == 3
  puts "a is three"
else
  puts "I don't know what a is"
end
```

You can also use a lambda in `when` for readability:

```
case a
when ->(n){n == 1 || n == 2}
  puts "a is one or two"
when when ->(n){n <= 3}
  puts "a is at least 3"
else
  puts "I don't know what a is"
end
```

Things to note:

-   The `,` in `when 'A', or 'B'` means “or”
-   The default block is under `else`
-   `when` _can_ accept regex or procs. For a full list of things you can do with `when` see [things you can do](https://stackoverflow.com/questions/4467538/what-does-the-operator-do-in-ruby) `[===](https://stackoverflow.com/questions/4467538/what-does-the-operator-do-in-ruby)`.
