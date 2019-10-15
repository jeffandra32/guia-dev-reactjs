#versão do node
FROM node:12.12.0-alpine as build

#diretótio
WORKDIR /app

#copia arquivos pra dentro da imagem
COPY package*.json ./

#instala as depedências yarn || npm
RUN yarn

