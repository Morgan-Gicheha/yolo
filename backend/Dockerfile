# Use the official Node.js Alpine image as the base image
FROM node:16-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 5000

# Define the command to run the application
CMD ["npm", "start"]
