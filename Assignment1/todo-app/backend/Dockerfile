<<<<<<< HEAD
# Backend Dockerfile
FROM node:18-alpine

WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install --production

# Copy source code
COPY . .

# Expose the backend port
EXPOSE 5000

# Start the server
=======
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 5000
>>>>>>> 4e9f7a652adff2174ea54b7c496581feb69e2a0e
CMD ["node", "server.js"]