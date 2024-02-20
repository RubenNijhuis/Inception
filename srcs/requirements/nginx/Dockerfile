# Use Alpine Linux as the base image
FROM alpine:latest

# Update the package repository and install Nginx
RUN apk update && apk add nginx

# Create a directory for Nginx to store its runtime data
RUN mkdir -p /run/nginx

# Copy the custom Nginx configuration file
COPY nginx.conf /etc/nginx/nginx.conf

# Create a directory to store HTML files
RUN mkdir -p /usr/share/nginx/html

# Copy HTML files to the container
COPY html /usr/share/nginx/html

# Expose port 80 for Nginx
EXPOSE 80

# Start Nginx in the foreground when the container runs
CMD ["nginx", "-g", "daemon off;"]