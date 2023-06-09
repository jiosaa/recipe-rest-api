## REST API 

# project creation actions with docker
i. create repo
ii. create access token on hub.docker.com
iii. back to github and goto settings -> secrets then add DOCKERHUB_USER and DOCKERHUB_TOKEN 


# using docker with django
->drawback
- VSCode unable to access interprator
- more difficult to use integrated features - means we can't use interactive debbugger and linting tools that come with VS

# configuring docker
- the command
  docker-compose run --rm appname sh -c "python3 manage.py collectstatic"

# after creating a project
1. create requirements.txt
2. create Dockerfile
3. create .dockerignore
4. build docker  using "docker build ."
5. create docker-compose.yml
6. run docker-compose build
7. adding listing(code formatting) and testing

# linting
   -> handling linting
     - install flake8 package
     - run it through docker compose ("docker-compose run --rm app sh -c "flake8")

    ### configure flake8
        - create requirements.dev.txt
        - then run docker-compose build
        - configuring ( create flake8 file in recipe-app)
        - run command ("docker-compose run --rm recipe-app sh -c "flake8" ")


# testing
  - we use django test suite
  - setup test per Django app
  - run tests through docker compose
    "docker-compose run --rm sh -c "python manage.py test"

8. Create django project in recipe-app folder using command [docker-compose run --rm recipe-app sh -c "django-admin startproject recipe-app ."]

9. start service by using [ docker-compose up]



# GITHUB ACTIONS
- USED for deployment, unit testing and linting
-> how it works  
   i. trigger (pushing to github)
   ii. Job (e.g. run unit test)
   iii. Result (successful)

### steps to create github actions
 - create folder [.github] in root directory
 - create folder [.github/workflow]
 - create file [.github/workflow/checks.yml]







 # TESTING IN DJANGO



10. adding db service to docker-compose.yml file
11. configuring db with django (install psycopg2 for postgresql db)
12. install postgresql adapter (psycopg2) - we add some line into Dockerfile then updating requirements.txt and then run [docker-compose build]
13. configure db into settings.py