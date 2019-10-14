FROM node:10.16.3-alpine

RUN set -ex \
  && apk update \
  && apk add --no-cache git openssh bash \
  && rm -rf /tmp/*

RUN npm config set proxy ${HTTP_PROXY}
