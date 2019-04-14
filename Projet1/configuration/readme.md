# Configuration

All reading lists are optional and only helps for a better understanding of the tool.

## Rails new

### Why?

Creating the app, "_the right way_" will help the process as changing the default after is a bit tedious/difficult in rails.

### Must have

- [ ] Postgresql
- [ ] No Tests framework

### Todo

- [ ] Read through the `rails new --help` documentation
- [ ] Create the app

## Ruby version/gemset

### Why?

Setting the ruby version ensure that every developer AND production will use the same ruby version.

The ruby gemset is a tool to ensure that our project's gems will only be installed and visible by it. Same, it won't be able to see other project gems.
It helps NOT having things that works in dev but not in production.

### Must Have

- [ ] .ruby-version: Must be 2.6.2
- [ ] .ruby-gemset: Must be any uniq string related to the project

### Reading List

- https://rvm.io/workflow/projects#project-file-ruby-version
- https://rvm.io/gemsets/basics

## Install

Each time you add a gem, remember to run bundle install ;)

## Rubocop

### Why?

Rubocop will help us to keep our code clean, and consistant and will warn us about various optimizations/best practices along the way.

### Must have

- [ ] Add [rubocop](https://github.com/rubocop-hq/rubocop)
- [ ] Add [relaxed rubocop](https://relaxed.ruby.style/)
- [ ] Add [rubocop-rspec](https://github.com/rubocop-hq/rubocop-rspec)
- [ ] Should look like [base_robocop.yml](https://raw.githubusercontent.com/denispasin/mvc_exercise/dine/.rubocop.yml). Be sure to understand Everything in it.
- [ ] Run it and fix any issue already there (hint: `rubocop -a` try to autofix everything)

### Reading list

- https://github.com/rubocop-hq/ruby-style-guide
- https://github.com/rubocop-hq/rails-style-guide

## Rspec

### Why?

We need a test framework right away. This way, rails will generate the different files correctly.
I'd rather like Rspec as its syntax is more readable and the tests look good.

### Must have

- [ ] [rspec-rails](https://github.com/rspec/rspec-rails)
- [ ] Install rspec in the app (`rails generate rspec:install`)
- [ ] basic `.rspec` config must include rails_helper by default
- [ ] Line `config.order = :random` in `spec_helper.rb` must be uncommented. Other options are up to you.

### Nice to have

I advice adding a directory `spec/support` and autoload everything from it in your `rails_helper.rb`:

```ruby
Dir["./spec/support/**/*.rb"].sort.each { |f| require f }
```

### Reading List

- [Short videos about rspec](http://rspec.info/)
- [Getting started](https://relishapp.com/rspec/docs/gettingstarted)
- [List of matchers](https://relishapp.com/rspec/rspec-expectations/v/3-7/docs/built-in-matchers)
- [Hooks](https://relishapp.com/rspec/rspec-core/v/3-7/docs/hooks/before-and-after-hooks)
- [Rspec subject](https://relishapp.com/rspec/rspec-core/v/3-7/docs/subject/explicit-subject)
- [Style guide for rspec](http://www.betterspecs.org/)
- [@Zaratan's article about rspec basics](https://www.zaratan.fr/posts/2018-03-02-turtle-family-1/)

## Shoulda

### Why?

Shoulda matcher helps to verify a lot of things regarding models which would otherwise be difficult to test

### Must Have

- [ ] Shoulda matcher installed and configured

### Todo

- [ ] Add the [Gem](https://github.com/thoughtbot/shoulda-matchers)
- [ ] [Configure the Gem](https://github.com/thoughtbot/shoulda-matchers#rails-apps)

### Reading List

- [Shoulda matcher list](https://github.com/thoughtbot/shoulda-matchers#matchers)

## Factory Bot && Faker

### Why?

It's really bothersome to create instance of model all the time in our tests.
Factory bot (used with faker) will help us to create randomized model instance created in DB for our tests.
It will also creates associated models and allows us to just override what we need to test.

Nobody wants to type `@my_model = MyModel.create(name: 'important', description: 'xxx', short_description: 'owi', age: 23, array_attribute: [1,2,3] …)` over and over in their test.
Using `create(:my_model, name: 'important')` is way more easier.

### Must have

- [ ] [Factory bot](https://github.com/thoughtbot/factory_bot_rails)
- [ ] factory_bot is [configured with rspec](https://github.com/thoughtbot/factory_bot/blob/master/GETTING_STARTED.md#rspec)
- [ ] [Faker](https://github.com/stympy/faker) (Remember to `require 'faker'` near the top of your `rails_helper.rb`)

### Reading List

- Read [Factory Bot Doc](https://github.com/thoughtbot/factory_bot/blob/master/GETTING_STARTED.md)
- Read faker readme

## SimpleCov

### Why?

Tracking the coverage of all our code is helpful and tells you what should be tested next.
Sometimes we think that we have enough tests, sometimes we don't. How about having a metric that will give us a better vision ?

For this, there's coverage. It helps us to know what have been tested and what haven't.
However, we can still write stupid tests without any expect that cover all the lines.

Consider it as a maximum of trust you can have in a codebase.

### Must have

- [ ] Add [simplecov](https://github.com/colszowka/simplecov#getting-started)
- [ ] Add the coverage directory to .gitignore
- [ ] Configure simplecov to run with rspec: `SimpleCov.start 'rails'`

### Reading list

- [Configuring simplecov](https://github.com/colszowka/simplecov#configuring-simplecov)

## Annotate

### Why?

It's easier to be able to know what is in DB on top of relevant files.

### Must have

- Add [annotate](https://github.com/ctran/annotate_models) gem
- Install it: `rails g annotate:install`

## dotenv

### Why?

It's practical to be able to set env variables without commiting them.
In heroku, everything will also come as env variables.

### Must Have

- [ ] install [dotenv](https://github.com/bkeepers/dotenv)
- [ ] add `.env` to .gitignore
- [ ] Be sure to generate a commited `.env_sample` which will contain the different keys needed into your `.env` but with mock values

## Docker-compose

### Why?

Using services not installed directly on host allows us to have:

- A better control of which version is used
- An easy way to destroy everything: `docker-compose down -v`
- An easy way to install some services for every dev
- Services are compartimented by app (working on two projects won't impact each other)

### Must have

- [ ] Copy docker-compose.yml from [previous project](https://raw.githubusercontent.com/denispasin/mvc_exercise/master/docker-compose.yml)
- [ ] Be sure to understand what is what.

## Database

Copy paste the configuration from [previous project](https://github.com/denispasin/mvc_exercise/blob/master/config/database.yml) so your database will work with a dockerized postgres.

## Husky

### Why ?

Husky is a tool to run commands before each commit and push. It block a commit/push if everything is not perfect.

We are all lazy. Husky helps us by forcing us to keep our code base clean and tested.

### Must have

- [ ] check your version of node should be > 6 and npm installed
- [ ] `npm install --dev husky` https://github.com/typicode/husky
- [ ] Configure it for running before each commit: rubocop
- [ ] Configure it for running before each push: rspec
- [ ] Don't forget to add `node_modules` inside your `.gitignore`

## Guard (optional)

### Why ?

Guard is a tool that watch for any change on certain files and then run some commands.
It's useful 'cause we can use it to never forget to run tests/linting before commit/push.

### Must have

- [ ] [Guard](https://github.com/guard/guard) configured for the project
- [ ] Auto test with: [guard-rspec](https://github.com/guard/guard-rspec)
- [ ] Auto lint with: [guard-rubocop](https://github.com/yujinakayama/guard-rubocop)

### Reading list

- [Configure Guard](https://github.com/guard/guard/wiki/Guardfile-DSL---Configuring-Guard)
