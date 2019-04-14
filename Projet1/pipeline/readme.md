# Heroku pipeline

### Why?

A fully automated deployment process will ensure that nobody ever push the wrong branch in deployment and will ensure that what is on Heroku is always up to date. It will also give us a staging env identical to production where we can test our feature one last time before updating the production (the only env clients see).

### Must have

- [ ] Staging
- [ ] Prod
- [ ] Auto deploy master on Staging
- [ ] Deploy should run migrations

Each should have:

- [ ] Postgres

**Important**: Do not configure your term to be able to talk to heroku.

### Todo

- [ ] Create a heroku pipeline
- [ ] Create the staging app
- [ ] Create the prod app
- [ ] Add postgres on both
- [ ] Add a [Procfile](https://devcenter.heroku.com/articles/getting-started-with-rails5#procfile) to the App
- [ ] Add a [release step](https://devcenter.heroku.com/articles/release-phase) in your procfile to run the migrations
- [ ] Configure heroku so it auto deploys master on staging.
- [ ] Deploy it
- [ ] Promote to production
- [ ] Check that everything is right by running a console in both env.

### Reading list

- https://www.heroku.com/dynos
- https://devcenter.heroku.com/articles/pipelines

### Bonus

Activate [Review apps](https://devcenter.heroku.com/articles/github-integration-review-apps)
