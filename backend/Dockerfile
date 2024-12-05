# backend/Dockerfile
# Use the Node.js LTS image
FROM node:22-alpine

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the application files
COPY . .

# Expose the port the backend server will run on
EXPOSE 5000

# Command to start the server
CMD ["npm", "start"]
