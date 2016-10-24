#
# Nginx Dockerfile
#
# https://github.com/dockerfile/nginx
#

# Pull base image.
FROM centos:7

# Install Nginx.
RUN yum -y install epel-release
RUN yum -y install nginx

RUN echo -e "\ndaemon off;" >> /etc/nginx/nginx.conf

RUN mkdir /etc/nginx/sites-enabled \
    /etc/nginx/certs

# Define mountable directories.
VOLUME ["/etc/nginx/sites-enabled", "/etc/nginx/certs", "/etc/nginx/conf.d", "/var/log/nginx", "/usr/share/nginx"]

# Define working directory.
WORKDIR /etc/nginx

# Define default command.
CMD ["nginx"]
#CMD ["tail", "-f", "/dev/null"]

# Expose ports.
EXPOSE 80 443