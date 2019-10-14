FROM NODE:10-alpines as build

#RUN npm config set proxy ${HTTP_PROXY}
RUN set -ex \
    && apk update \
    && apk add --no-cache git \
    && rm -rf /tmp/*

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . ./
RUN npm run build-dev

FROM httpd:2.4.35-alpine
RUN mkdir -p /vox/analise-livro-front
COPY --from=build /app/dist /vox/analise-livro-front/dist
RUN chgrp -R www-data /vox/analise-livro-front
COPY ./docker/apache/conf/httpd-vhosts.conf /usr/local/apache2/conf/extra/httpd-vhosts.conf
COPY ./docker/apache/conf/httpd-ssl.conf /usr/local/apache2/conf/extra/httpd-ssl.conf
COPY ./docker/apache/conf.cert/voxtecnologia.com.br.crt /usr/local/apache2/conf/server.crt
COPY ./docker/apache/conf.cert/voxtecnologia.com.br.key /usr/local/apache2/conf/server.key
COPY ./docker/apache/conf/httpd.conf /usr/local/apache2/conf/httpd.conf
EXPOSE 80
