# frontend/Dockerfile
# Use Node.js for building the frontend
FROM node:22-alpine AS builder

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the application files and build the app
COPY . .
RUN npm run build

# Use Nginx to serve the built files
FROM nginx:alpine

# Copy the built files to Nginx's default static file directory
COPY --from=builder /usr/src/app/build /usr/share/nginx/html

# Expose the default Nginx port
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
