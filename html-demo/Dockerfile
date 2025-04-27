# Use the official Nginx image
FROM nginx:latest

# Remove the default nginx index page
RUN rm /usr/share/nginx/html/index.html

# Copy our custom HTML page
COPY index.html /usr/share/nginx/html/index.html

# Expose port 80
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
