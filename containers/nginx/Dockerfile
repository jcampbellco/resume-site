#
# Nginx Dockerfile
#
# https://github.com/dockerfile/nginx
#
# cd ~/resume-site
# docker build containers/web -t jcampbell.co
# docker run -v /home/admin/resume-site/app/:/usr/share/nginx/html -d -p 8080:80 -p 4443:443 jcampbell.co
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

# Expose ports.
EXPOSE 80 443