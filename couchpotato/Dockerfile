# lets use my default centos7 base image
FROM hoogwater/base

MAINTAINER Leon (hoogwater) Vliegenthart

# Need git, but run yum clean all after each yum command to clear cache for this layer
RUN yum install -y git python-pip openssl gcc openssl-devel && yum clean all
RUN yum install -y python-devel && yum clean all
RUN yum install -y libffi-devel && yum clean all
RUN pip install pyopenssl --upgrade

# get latest git data
RUN git clone https://github.com/RuudBurger/CouchPotatoServer.git

# add user for media
RUN useradd -u 1000 media

# add start.sh
ADD start.sh /start.sh

# make executable
RUN chmod +x /start.sh

# chown the git clone
RUN chown -R media:media /CouchPotatoServer

# usuall runs on 5050
EXPOSE 5050

# switch to user media
USER media

# CMD can be easily overwritten for troubleshooting
CMD ["/start.sh"]
