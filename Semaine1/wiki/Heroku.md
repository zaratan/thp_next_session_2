In this section, we will be setting up a Heroku pipeline with staging and production environments. 

In your dashboard : 
* Create a pipeline
* Create a staging application
* Configure automatic deployments to staging
* Create a production application

In both environments : 
* add a redis resource
* add a sendgrid resource
* activate your sidekiq worker
* add necessary environment variables

Once your application works properly in staging, promote manually to production.