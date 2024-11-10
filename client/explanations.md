# Dockerfile breakdown


`FROM node:18-alpine AS build`

selecting node alpine image because it is lighteer version


`WORKDIR /app`

defining working directory

`COPY package*.json ./`

copying package.json first and installing requiremnts, this will be cached and save time in subsequest builds

`COPY . .`


copying all the project files to the image

`RUN npm run build`
builng the react app for production

`FROM nginx:alpine`

selecting base image of a our web browser as nginx, alpine version will be smaller in space.


`COPY --from=build /app/build /usr/share/nginx/html`



Copying the build files from the previously defined image, then copying the files in the build folder to the Nginx HTML directory to be served

`EXPOSE 80`

exposing the default port for nginx, which is 80


`CMD ["nginx", "-g", "daemon off;"]`

booting up th nginx server


## building the image

`docker build -t gicheha/ip_frontend:v1.0.1 .`


## Pushing the image to docker hub
`docker push gicheha/ip_frontend:v1.0.1`

## running the image locally
`docker run -p 80:80 gicheha/ip_frontend:v1.0.0`