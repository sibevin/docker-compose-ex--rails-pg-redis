# A docker-compose example for rails + pg + radis

## Setup

### In folder

* Clone your rails app repo to `shared_folder/rails/your-rails-app`
* Build docker images: `docker-compose build`
* Run docker compose: `docker-compose up`
* Open another console and connect to rails container: `docker exec -it devenvdocker_rails_1 bash`

### In rails container

* Go to your rails app folder: `cd /app/your-rails-app`
* Install gems: `bundle`
* Change your database.yml, to connect db with following settings:
```
POSTGRES_PASSWORD=rpr_pw
POSTGRES_USER=rpr_user
POSTGRES_DB=rpr_db
```
* Setup database: `rails db:create db:migrate db:seed`
* Run server: `rails s -b 0.0.0.0 -p 3000`

## Run

### In dev-env-docker folder

* Run docker compose: `docker-compose up`
* Open another console and connect to rails container: `docker exec -it devenvdocker_rails_1 bash`

### In rails container

* Go to your rails app folder: `cd /app/your-rails-app`
* Run server: `rails s -b 0.0.0.0 -p 3000`

## Shotdown

### In rails container

* ctrl+c to stop rails server

### In dev-env-docker folder

* ctrl+c to stop docker-compose
* Remove containers: `docker-compose down`

## Container Information

### Rails

* Rails server: `http://localhost:3000`
* All gems are installed in `shared_folder/bundle/gems`
* You can put ENVs in `rails/app.env`
* A docker image is built and tagged with `rpr/rails:5.0.0.1`
* Use offical image: ruby:2.4.1

### Database

* postgres server: `http://localhost:5432`
* Use offical image: postgres:9.6.4
* A default database is created, please reference docker-compose.yml for details

### Redis

* redis server: `http://localhost:6379`
* Use offical image: redis:3.2.10

