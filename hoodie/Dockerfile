FROM debian:wheezy

MAINTAINER GoAppes <dev@goappes.com>

# install couchdb
FROM klaemo/couchdb

# install node
FROM goappes/nodejs

RUN su nodejs

# hoodie
RUN npm install -g hoodie-cli

# this avoid hoodie only accepting connections from localhost (kinda pointless in a docker world)
ENV HOODIE_BIND_ADDRESS 0.0.0.0
ENV COUCH_URL http://couchdb:5984

EXPOSE 6001 6002 
CMD ["/bin/bash"]