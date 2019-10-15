#versão do node
FROM node:12.12.0-alpine as build

#diretótio
WORKDIR /app

#copia arquivos pra dentro da imagem
COPY package*.json ./

#instala as depedências yarn || npm
RUN yarn

#copiar todos os códigos fontes
COPY . ./

#informar qual porta o serviço está rodando
EXPOSE 80

#informar comandos para execução no package.js
CMD [ "yarn", "start" ]

