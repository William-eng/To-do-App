# Base image for Node.js application
FROM  node:14.21.1-alpine

WORKDIR /app
COPY package*.json .
RUN npm install jsonwebtoken@7.4.3
RUN npm install


COPY . .

EXPOSE 8082
CMD ["npm", "start"]
