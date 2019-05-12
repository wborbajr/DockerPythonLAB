# User the Nginx image
#FROM nginx:alpine
FROM nginx:latest

# The maintainer of image
MAINTAINER Waldir Borba Junior <wborbajr@gmail.com>

# Remove the default nginx.conf and replace with our own nginx.conf
RUN rm /etc/nginx/nginx.conf
ADD nginx.conf /etc/nginx/

RUN rm /etc/nginx/conf.d/default.conf
ADD family_recipes.conf /etc/nginx/conf.d/
