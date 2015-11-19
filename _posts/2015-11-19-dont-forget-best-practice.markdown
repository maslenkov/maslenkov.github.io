---
layout: post
title:  "What are missed in one of my projects?"
date:   2015-11-19 19:14:49
categories: best-practices
---
### Background

Few months ago I joined to growing up project. And problems which I got when set up project enforce me to write this article.

### How can I prepare my project for future or for a next programmer?

I prepare list of issues which make my cry in this project. Their are ordered by priority. And broken down to two groups.

#### In general

* Write tests! It is the first. Because tests not only additional code. Their get you regression tests base and documentation. Also they help you find unused code and removing it without problems.
* Readme. If your project could not be set up with standard actions like: `git clone... && rake db:create db:setup` and `rails server` then you should provide instructions.
* [Delete your code][delete-your-code]. Delete commented code and unnecessary/unused code. Try to write self-documented code instead of code with comments.

#### In my humble opinion

* Migrations.

  * Don't add data through migrations. Use seeds or add rake task if seeds don't good for your purpose. I use seed.rb to set important things for project such as some configs. Seed_fu for populating. But if I need add some data after migration I use rake tasks. You can use rake task for populating too. But don't use migrations for this purpose.
  * Some times when you very good understand what you do you can modify data with migration. But in this situation this migration should work in all environments. Don't coupling to things like IDs.
  * Reversible migrations. Use change. If your action is not reversible use `reversible` with blank body or divide it to up and down. Last can be blank if it is necessary.

* Read about best practice. Try to follow them.
* Use modern and adoptive tools if it is possible. For example use `pry-rails` inside rails app instead of `pry`.

[delete-your-code]: https://youtu.be/Oj4vXMRenFo
