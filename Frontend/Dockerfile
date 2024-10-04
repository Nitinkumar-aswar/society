# Frontend Dockerfile

# Step 1: Build the React app
FROM node:16 AS build

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY frontend/package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the app code
COPY frontend/ .

# Build the app
RUN npm run build

# Step 2: Serve the app using a lightweight server
FROM nginx:alpine

# Copy the build output to NGINX's public folder
COPY --from=build /app/build /usr/share/nginx/html

# Expose the port
EXPOSE 80

# Command to run NGINX
CMD ["nginx", "-g", "daemon off;"]

