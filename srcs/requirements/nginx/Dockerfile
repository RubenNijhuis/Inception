# Use Alpine Linux as the base image
FROM alpine:latest

# Update the package repository and install Nginx
RUN apk update && apk add nginx

# Create a directory for Nginx to store its runtime data
RUN mkdir -p /run/nginx

# Copy the custom Nginx configuration file
COPY config/nginx.conf /etc/nginx/nginx.conf

# Expose port 80 for Nginx
EXPOSE 8080

# Start Nginx in the foreground when the container runs
CMD ["nginx", "-g", "daemon off;"]