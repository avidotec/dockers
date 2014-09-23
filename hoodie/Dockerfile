FROM debian:wheezy

MAINTAINER GoAppes <dev@goappes.com>

ENV CI true
# this avoid hoodie only accepting connections from localhost (kinda pointless in a docker world)
ENV HOODIE_BIND_ADDRESS 0.0.0.0

# Update the package repository
RUN apt-get update; apt-get upgrade -y; apt-get install -y \
  locales \
  git

FROM klaemo/couchdb

FROM goappes/nodejs

# hoodie
RUN npm install -g hoodie-cli
 
EXPOSE 6001 6002 
CMD ["/bin/bash"]