# lets use my default centos7 base image
FROM hoogwater/base

MAINTAINER Leon (hoogwater) Vliegenthart

# Install packages 
RUN yum install -y shellinabox openssh-clients && yum clean all

# add user for media
RUN useradd -u 1000 ssh

# usuall runs on 8081
EXPOSE 4200

# CMD can be easily overwritten for troubleshooting
CMD /usr/sbin/shellinaboxd -v -t --service "/:ssh:ssh:/home/ssh:/bin/bash"
