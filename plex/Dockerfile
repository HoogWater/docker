# lets use my default centos7 base image
#FROM hoogwater/base
FROM centos:7

MAINTAINER Leon (hoogwater) Vliegenthart

# install packages and clean up directly after to not get a bloated container
ADD plex.repo /etc/yum.repos.d/plex.repo
RUN yum install -y plexmediaserver && yum clean all

RUN yum install -y dbus && yum clean all

# add user for media, start.sh will switch to media user
RUN useradd -u 1000 media

# usually runs on 8081
EXPOSE 32400

# There are other ports for discovery, but we use --net=host so no need to expose ports

# add start script
ADD start.sh /start.sh

# make executable
RUN chmod +x /start.sh

# CMD can be easily overwritten for troubleshooting
CMD ["/start.sh"]
