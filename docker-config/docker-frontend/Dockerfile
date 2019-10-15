#versão do node
FROM node:12.12.0-alpine as builder

#diretótio
WORKDIR /usr/src/app

#copia arquivos pra dentro da imagem
COPY package*.json ./

#instala as depedências yarn || npm
RUN yarn

#copiar os códigos do src
COPY src/ ./src/

#copiar todos os códigos fontes do public
COPY public/ ./public/

#construir a aplicação para produção
RUN yarn run build

#service externo
FROM nginx:1.15.5

COPY --from=builder /usr/src/app/build/ /usr/share/nginx/html

#informar qual porta o serviço está rodando
EXPOSE 80


# RUN set -ex \
#  && apk update \
#  && apk add --no-cache git \
#  && rm -rf /tmp/*

#WORKDIR /app
#COPY package*.json ./
#RUN npm install
#COPY . ./
#RUN npm run build-dev

#FROM httpd:2.4.35-alpine
#RUN mkdir -p /vox/analise-livro-front
#COPY --from=build /app/dist /vox/analise-livro-front/dist
#RUN chgrp -R www-data /vox/analise-livro-front
#COPY ./docker/apache/conf/httpd-vhosts.conf /usr/local/apache2/conf/extra/httpd-vhosts.conf
#COPY ./docker/apache/conf/httpd-ssl.conf /usr/local/apache2/conf/extra/httpd-ssl.conf
#COPY ./docker/apache/conf.cert/voxtecnologia.com.br.crt /usr/local/apache2/conf/server.crt
#COPY ./docker/apache/conf.cert/voxtecnologia.com.br.key /usr/local/apache2/conf/server.key
#COPY ./docker/apache/conf/httpd.conf /usr/local/apache2/conf/httpd.conf
#EXPOSE 80
