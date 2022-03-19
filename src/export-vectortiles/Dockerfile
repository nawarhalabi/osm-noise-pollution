FROM node:5
MAINTAINER Lukas Martinelli <me@lukasmartinelli.ch>

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

RUN apt-get update
RUN apt-get -y install libstdc++6

RUN npm install -g tl@0.8.*
RUN npm install -g mapnik@3.5.x
RUN npm install -g mbtiles@0.8.x
RUN npm install -g tilelive@5.12.x
RUN npm install -g tilelive-tmsource@0.4.x
RUN npm install -g tilelive-vector@3.9.x
RUN npm install -g tilelive-bridge@2.3.x
RUN npm install -g tilelive-mapnik@0.6.x

VOLUME /data/tm2source /data/export
ENV SOURCE_PROJECT_DIR=/data/tm2source EXPORT_DIR=/data/export TILELIVE_BIN=tl
COPY . /usr/src/app/

CMD ["/usr/src/app/export-local.sh"]
