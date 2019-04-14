# Configuration

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

### Shoulda

### Factory Bot

### SimpleCov

### Faker

## Annotate

## dotenv

## Docker && Docker-compose

## Database

## Husky

## Guard (optional)
