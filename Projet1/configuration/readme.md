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

### Must have

- [ ] Simple cov [installed](https://github.com/colszowka/simplecov#getting-started)
- [ ] Simple configuration: `SimpleCov.start 'rails'`

## Annotate

## dotenv

## Docker && Docker-compose

## Database

## Husky

## Guard (optional)
