# Taking a very small base
FROM nginx:stable-alpine
# Upgrade all packages
RUN apk upgrade --force
# Copy the confg file
COPY fe.conf /etc/nginx/conf.d/default.conf
# Copy static files
COPY /location/to/static/files /var/www/app
# Start nginx on container run
ENTRYPOINT ["nginx", "-g", "daemon off;"]
