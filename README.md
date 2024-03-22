# kanban_app
This is the 3 tier kanban app

 This project is an implementation of such board and made of 3 separate Docker containers that holds:

   - PostgreSQL database
   - Java backend (Spring Boot)
   - Angular frontend

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


## Output:
![image](https://github.com/Farhan-Ahmed-Netsmartz/kanban_app/assets/160687843/54b2f00a-64b2-462f-afa9-58bc4b6a154f)

![Screenshot from 2024-03-22 16-00-58](https://github.com/Farhan-Ahmed-Netsmartz/kanban_app/assets/160687843/dbdf3201-82b5-4590-85d4-b4b9363f788e)

![Screenshot from 2024-03-22 15-59-07](https://github.com/Farhan-Ahmed-Netsmartz/kanban_app/assets/160687843/3984568e-87e9-4f72-ab5b-75262200bd2f)

For more got to its original repo: https://github.com/wkrzywiec/kanban-board.git
