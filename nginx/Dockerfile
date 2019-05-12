# User the Nginx image
FROM nginx:alpine

# The maintainer of image
MAINTAINER Waldir Borba Junior <wborbajr@gmail.com>

# Remove the default nginx.conf
RUN rm /etc/nginx/conf.d/default.conf

# Replace with our own nginx.conf
COPY nginx.conf /etc/nginx/

CMD ["nginx", "-g", "daemon off;"]
