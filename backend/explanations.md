I used FROM node:16-alpine becasue is more or a bare metal version of node, meaning it will save space  in the final resulting image


WORKDIR /app

deifning the working directory

COPY package*.json ./

copying the package .json first, ths will save time when rebuilding the image bacause it will be saved in cache



COPY . .

copying all the files into the image.

EXPOSE 5000

exposing port

CMD ["npm", "start"]

running the start up command to start the API




 building the image.
-------------------
docker build -t gicheha/ip_backend:v1.0.0 .


 pushing the image to dockerhub
 ------------------
docker push gicheha/ip_backend:v1.0.0


Running the image locally
----------------------------------

docker run -p 5000:5000 docker.io/gicheha/ip_backend:v1.0.0