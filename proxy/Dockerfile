# lets use my default centos7 base image
FROM hoogwater/base

MAINTAINER Leon (hoogwater) Vliegenthart

# Install packages 
RUN yum install -y httpd mod_ssl && yum clean all

# run on httpd
EXPOSE 443

#Add start script
ADD start.sh /start.sh
RUN chmod +x /start.sh

# CMD can be easily overwritten for troubleshooting
CMD ["/start.sh"]
