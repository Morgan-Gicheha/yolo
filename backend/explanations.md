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


 pushing the image to dockerhub
 ------------------



Running the image locally
----------------------------------

