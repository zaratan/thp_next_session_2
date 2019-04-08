In this section, we will be setting up the mailer in the development and test environments. 

We will be setting up docker containers with a very basic setup in order to run our services. The reason why we chose to proceed with this devops tool is that many issues can arise from the variety of different software configurations that are out there starting with operating systems. Also, working with containers is more secure for your computer. Lastly, even if this course isn't about docker, we believe it's a good idea to know how to dockerize a simple rails app.

* run `docker-compose up postgres redis maildev`
* modify your **config/environments/development.rb** and **config/environments/test.rb** files according to the documentation for maildev
* run `sidekiq -C config/sidekiq.yml`
* run `rails c` and check that the creation of an admin triggers the sending of an e-mail
* in your browser, check the url : "localhost:1081" to confirm the e-mail

Create a mailer service that can be triggered in the back office : 
On user page --> send offer
