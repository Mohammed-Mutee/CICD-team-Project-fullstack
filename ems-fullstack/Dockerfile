# STAGE 1: Build the React application
FROM node:20-alpine AS builder

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
# This command creates the final static files in the /app/dist folder
RUN npm run build


# STAGE 2: Serve the application using Nginx
FROM nginx:stable-alpine

# Copy the static files from the build stage to the Nginx html directory
COPY --from=builder /app/dist /usr/share/nginx/html

# Copy our custom Nginx configuration
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Expose port 80
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]