FROM debian:wheezy

MAINTAINER GoAppes <dev@goappes.com>

# Install Node
ENV NODEJS_VERSION 0.10.28
# this avoids asking for couch admin pw

RUN apt-get update; apt-get upgrade -y; apt-get install -y \
  locales \
  git \
  curl

RUN   \
  cd /opt && \
  curl -O http://nodejs.org/dist/v$NODEJS_VERSION/node-v$NODEJS_VERSION-linux-x64.tar.gz && \
  tar -xzf node-v$NODEJS_VERSION-linux-x64.tar.gz && \
  mv node-v$NODEJS_VERSION-linux-x64 node && \
  cd /usr/local/bin && \
  ln -s /opt/node/bin/* . && \
  rm -f /opt/node-v$NODEJS_VERSION-linux-x64.tar.gz

RUN useradd -d /var/www -m nodejs
RUN su nodejs

# hoodie
RUN npm install -g gulp
RUN npm install -g bower
 
# Alt dependencies
RUN mkdir /var/www/app
RUN chown nodejs:nodejs -R /var/www/app
WORKDIR /var/www/app
