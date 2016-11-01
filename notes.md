**Travis Continuous Integration Suite**

- everyone pushes to Github and Travis is monitoring repos, doing tests, and deploying to production environment
- all you have to do is do unit tests, push to Github, and the regression testing/deployment is taken care of by Travis 

CONTINUOUS INTEGRATION<br>
*"Purpose is to prevent integration issues from divergent code causing merge conflicts."<br>*
Many services that provide CI. Travis CI is just one suite. 

If you don't have tests and you are just using Travis as a pipeline to Heroku, you aren't really utlizing what Travis can do for you. 

1. Set up account with Github user id on Travis site 
2. Give permission to certain public repos 
3. Add a file to the root directory of your project called '.traves.yml' <<- Travis will not do anything without this 
4. Git commit and watch Travis fail  
5. After project fails, add some things to .travis.yml file to make things work 
  - before deploying to Github, make sure to 'bundle install' 
  - run `travis encrypt $(heroku auth:token) --add deploy.api_key`<br>
    ^ need to be explicit about heroku app name because it will default to what your repo is named 
 - tell Travis what version of Ruby you want to use 


Monitors public repositories that users have flagged for Travis CI builds 
Creates a temp Linux env to run spec tests defined in project 
Travis will monitor repo for changes - when Travis observes pushes, it will start a small VM (virtual machine - fully operational operating system running in a virtual environment) that is destroyed when tests are done running 

https://github.com/pongo-pygmaeus/ar-teams-and-leagues-challenge-rails/blob/master/README.md


