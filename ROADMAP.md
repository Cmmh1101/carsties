# Microservice initial setup

## create new solution

> dotnet new sln 

## Create new web api

> dotnet new webapi -o src/AuctionService

## Add project to our project solution

> dotnet sln add src/AuctionService

## Run the app api

> cd src/AuctionService
> dotnet watch

## Setup Docker

- Create a file on the ROOT: docker-compose.yml
- Indentation is important

```
services:
  postgres:
    image: postgres
    environment:
      - POSTGRES_PASSWORD=18180888
    ports:
      - 5432:5432
    volumes:
      - pgdata:/var/lib/postgresql/data
volumes:
  pgdata:

```
- To run docker from the project ROOT use the command 
> docker compose up -d

## Start dotnet and update database

> dotnet ef database update

## Connect to postgres

- install postgreSQL extension
- Click the sidebar "postgres icon" 
- click the "+" to connect to a database
- add the info required
