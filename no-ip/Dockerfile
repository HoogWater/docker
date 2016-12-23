FROM alpine

MAINTAINER Mark de Jong <markdejong@gmail.com>

RUN adduser -S -u 1000 noip

RUN apk --update add \
  bash \
  curl && \
  rm -rf /var/cache/apk/*

ADD noip.sh /bin/noip.sh
RUN chmod 550 /bin/noip.sh && chown noip /bin/noip.sh

USER noip

VOLUME /config/noip

# Run script
CMD ["/bin/noip.sh"]
