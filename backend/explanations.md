This project is built with Node.js and runs on a lightweight Docker image using the `node:16-alpine` base image to minimize the final image size.


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






===========================================

=========================================




creating vagrant file
![alt text](<Screenshot from 2024-11-03 11-32-21.png>)

vagrant up command
![alt text](<Screenshot from 2024-11-03 11-55-28.png>)


tesing ansible playbook locally

![alt text](<Screenshot from 2024-11-03 12-26-35.png>)



command to launch playbook

sudo ansible-playbook -i hosts.ini playbook.yml



accessing the project in the host machin
![alt text](<Screenshot from 2024-11-03 23-01-01.png>)