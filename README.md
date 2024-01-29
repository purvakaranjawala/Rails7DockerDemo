# README for Docker Demo App

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version 3.1.2 and rails 7
* Database Postgresql

Start docker desktop to start daemon service for running docker.
Installation for ubuntoo https://docs.docker.com/desktop/install/ubuntu/
* Command
    build image: 
    ```
    docker build -t railsdockerapp .
    ```

    To See images:--

    ``` 
    docker images
    ```
    To see container:- 
    ```
    docker ps
    ```
     
    Run container:
    ```
    docker compose up
    ```

    Run migration for default database:- 
    ```
    docker compose run web bin/rails db:create db:migrate
    ```
    Gem added later

    ```
    docker compose run --rm web bundle install
    docker compose up --build
    ```

    Additional docker commands:-
    ```
    ## to stop services only
    docker-compose stop

    ## to stop and remove containers, networks..
    docker-compose down 

    ## to down and remove volumes
    docker-compose down --volumes
    ```

* In Browser 
    http://localhost:3002/posts

* NOTE:
    Note that you’re passing in db as the POSTGRES_HOST name because Docker Compose runs all the containers on a single network, and you can send requests to other containers through their hostname, which is the same as the service name. So in this example, the hostname for the database container is db since you’re using db as the service name in docker-compose.yml
