In this section, we will be creating **user** and **admin** resources with the devise gem.
We want both models to be **confirmable**, so we will be setting up a mailer system.

* follow the devise documentation in order to create an **Admin** and a **User** model with the **confirmable** option.
* run the migrations  
* update the routes
* modify the administration controller so that only signed_in admins are authorized
