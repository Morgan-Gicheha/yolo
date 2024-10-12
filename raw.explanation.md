compose file explanations.
---------------------------------------
sevices.


I have 3 services in my compose file,
    `1. mongo-db
    2. backend-microservice
    3. client-react-app

they all run in the same network, named ip-5-network.
The mongo db is the database, that has volumes defined by the follwoing command

    volumes:
      - mongo-data:/data/db
this will persist the data stored in the DB even when the mongo container has been restarted or deleted. this will mainatine the data



I have included indivitak explanations.md file for bot h client and back services in the below links.



this is the link to the dockerhub repository hilding the docker images

frontend

https://hub.docker.com/repository/docker/gicheha/ip_frontend/general

backend
https://hub.docker.com/repository/docker/gicheha/ip_backend/general




git workflow
---------------------------

to add a commit

git add .

to commit a staged commit

git commit -m "message"

pushing commit to github

git push


----------------------------

docker commands used.
-------------------------

building an image
docker build -t name:version <context>


pushing the image to dockerhub.

docker push imagename:version




