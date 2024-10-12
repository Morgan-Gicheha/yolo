## Dockerfiles

I have created individual explanations client and backend. below are the links to explanations.md for further explanations


[Client Explanation.md file](./client/explanations.md)

[backend Explanation.md file](./backend/explanations.md)



## Docker Compose File Explanation

### Services

This project consists of 3 services defined in the `docker-compose.yml` file:

1. **MongoDB**
   MongoDB acts as the database for the application. The volumes are defined as follows:

   ```yaml
   volumes:
     - mongo-data:/data/db


This volume persists the data stored in the database, ensuring that even if the MongoDB container is restarted or deleted, the data remains intact.

### Backend Microservice
The backend service handles all the business logic and API interactions. It connects to the MongoDB database. For more details, refer to the Backend Explanation.

### Client React App
The frontend is built using React, providing the user interface. More information can be found in the Client Explanation.


All services run within the same Docker network, named ip-5-network, allowing them to communicate seamlessly with one another.



## Docker Hub Repositories
You can find the Docker images for this project in the following repositories:

Frontend:  https://hub.docker.com/repository/docker/gicheha/ip_frontend/general
Backend:   https://hub.docker.com/repository/docker/gicheha/ip_backend/general




## Git Workflow

### adding Changes
To  add files to the staging area, run:

git add .

### Committing Changes
To commit the staged changes, use:

git commit -m "Your commit message"

### Pushing Changes
To push the committed changes to the GitHub repository:

git push



## Docker Commands
docker build -t name:version <context>


## Pushing an Image to Docker Hub

docker push imagename:version


