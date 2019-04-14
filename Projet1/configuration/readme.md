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
