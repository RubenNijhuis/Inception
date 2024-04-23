# Use Alpine Linux as the base image
FROM alpine:latest

# Update the package repository and install Nginx
RUN apk update && apk add nginx && apk add openssl

# Create a directory for Nginx to store its runtime data
RUN mkdir -p /run/nginx

RUN mkdir -p /etc/nginx/certs && \
	openssl req -newkey rsa:4096 -x509 -sha256 -days 365 \
	-nodes -out /etc/ssl/certs/certificate.crt \
	-keyout /etc/ssl/private/certificate.key \
	-subj "/CN=rnijhuis.codam.nl"

RUN ls -Rl /etc/ssl 

# Copy the custom Nginx configuration file
COPY config/nginx.conf /etc/nginx/nginx.conf

# Expose port 443 for Nginx
EXPOSE 443

# Start Nginx in the foreground when the container runs
CMD ["nginx", "-g", "daemon off;"]
