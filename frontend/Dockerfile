# Setting base image 
# FROM node:18-alpine3.18 as build
FROM node:18.18-alpine as vue-build

# Setting the work dir for the application
WORKDIR /app

# Copying node packages to working directory
COPY package*.json ./

# Installing the dependencies for the application
RUN npm install

# Copying other application files to work directoty
COPY . .

# Building production build
RUN npm run build

# Use a lightweight NGINX image with Alpine Linux as the production build
FROM nginx:1.25.2-alpine as production-build

# Set the working directory to /app/dist
WORKDIR /app/dist

# Overwrite the default NGINX configuration
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Copy the built Vue.js application from the frontend build stage
COPY --from=vue-build /app/dist .

# Expose port 80 to allow external connections
EXPOSE 80

# Specify the command to run NGINX in the foreground
CMD ["nginx", "-g", "daemon off;"]