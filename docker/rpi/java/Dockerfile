FROM base

RUN echo "http://nl.alpinelinux.org/alpine/v3.4/community/" >>/etc/apk/repositories && apk update && apk upgrade && apk add bash openjdk7-jre-base && rm -rf /var/cache/apk/*

CMD ["/bin/bash"]
