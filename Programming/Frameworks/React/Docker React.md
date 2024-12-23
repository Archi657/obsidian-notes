Dockerfile - Run command : 
ENV : REACT_APP_BACKEND_URL=http://localhost:8080
``` Bash
# Use an official Node.js runtime as the base image

FROM node:14

# Set the working directory

WORKDIR /app

# Copy package.json and package-lock.json

COPY package*.json ./

# Install dependencies
RUN npm install

# Install specific versions of FontAwesome packages
RUN npm install --save @fortawesome/free-solid-svg-icons@6.5.1 @fortawesome/react-fontawesome@0.2.0

RUN npm install --save @fortawesome/fontawesome-svg-core

ARG REACT_APP_HOST_IP_ADDRESS

ENV REACT_APP_HOST_IP_ADDRESS $REACT_APP_HOST_IP_ADDRESS

# Copy the rest of the application code
COPY . .

# Build the application
RUN npm run build

# Use a small Nginx image to serve the static files
FROM nginx:alpine

# Copy the build output to the Nginx html directory
COPY --from=0 /app/build /usr/share/nginx/html

# Expose port 80
EXPOSE 80

# Start Nginx server
CMD ["nginx", "-g", "daemon off;"]
```