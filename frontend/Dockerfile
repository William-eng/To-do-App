# Base image for building the frontend
FROM node:14.21.1-alpine


WORKDIR /app

COPY package*.json ./
RUN npm install 




# Copy all frontend files
COPY . ./

# Expose the application port
EXPOSE 8080

# Start the application
CMD ["npm", "run", "dev"]
