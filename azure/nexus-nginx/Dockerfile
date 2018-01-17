FROM nginx:1.13.8-alpine
MAINTAINER Daniel Eagle

# Remove unnecessary default file
RUN rm /etc/nginx/conf.d/default.conf

# Add configuration files
COPY config/nexus.conf /etc/nginx/conf.d/nexus.conf
COPY config/nginx.conf /etc/nginx/nginx.conf

# Remove write access from config files to protect from accidental damage
RUN chmod -v 0444 /etc/nginx/conf.d/nexus.conf \
  && chmod -v 0444 /etc/nginx/nginx.conf

# Create volume to persist SSL data
VOLUME /etc/ssl/certs/nginx

EXPOSE 5000 5001
