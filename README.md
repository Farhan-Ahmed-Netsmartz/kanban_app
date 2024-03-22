# kanban_app
This is the 3 tier kanban app
## First create network 

`docker network create kanban-network` 

## To run database final cmd: 

`docker build -t kanban-postgres ./Database/` 

`docker run -d --name kanban-postgres -v kanban_data:/var/lib/postgresql/data -p 5432:5432 --network kanban-network kanban-postgres` 

## To run backend final cmd: 

`docker build -t kanban-app ./kanban-app` 

`docker run -d --name kanban-app -p 8080:8080 --network kanban-network kanban-app` 

## To run ui final cmd: 

`docker build -t kanban-ui ./kanban-ui` 

`docker run -d --name kanban-ui --network kanban-network -p 4200:80 kanban-ui` 
