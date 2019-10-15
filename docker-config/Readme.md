# Instalando o Docker

### Documentação

_https://docs.docker.com/install/linux/docker-ce/ubuntu/_

_https://hub.docker.com/_

_https://docs.docker.com/compose/install/_

## Uninstall old versions

`sudo apt-get remove docker docker-engine docker.io containerd runc`

## Install Docker Engine - Community

- Install using the repository

`sudo apt-get update`

- Instale pacotes para permitir que o apt use um repositório sobre HTTPS:

`sudo apt-get install \ apt-transport-https \ ca-certificates \ curl \ gnupg-agent \ software-properties-common`

- Add Docker’s official GPG key:

`curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`

_Verifique se agora você possui a chave com a impressão digital 9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88, pesquisando os últimos 8 caracteres da impressão digital._

`sudo apt-key fingerprint 0EBFCD88 pub rsa4096 2017-02-22 [SCEA] 9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88 uid [ unknown] Docker Release (CE deb) <docker@docker.com> sub rsa4096 2017-02-22 [S]`

_Use o seguinte comando para configurar o repositório estável. Para adicionar o repositório noturno ou de teste, adicione a palavra noturno ou teste (ou ambos) após a palavra estável nos comandos abaixo. Aprenda sobre os canais noturnos e de teste._

`sudo add-apt-repository \ "deb [arch=amd64] https://download.docker.com/linux/ubuntu \ $(lsb_release -cs) \ stable"`

# Install Docker Compose

`Invoke-WebRequest "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-Windows-x86_64.exe" -UseBasicParsing -OutFile $Env:ProgramFiles\Docker\docker-compose.exe`

## Test the installation.

`docker-compose --version`

## Upgrading

`docker-compose migrate-to-labels`

## Uninstallation

`sudo rm /usr/local/bin/docker-compose`

---

## Comandos do Docker

<b>_Verificar versão do docker_</b>

- `docker version`

<b>_Construir o projeto e baixar as imagens_</b>

- `docker build -t <nome-diretorio> .`

<b>_Realiza um pull de uma imagem dentro do repositório do docker_</b>

- `docker pull`

<b>_Roda uma imagem no servidor local_</b>

- `docker run -d <nome-image>`

<b>_Roda o container dentro da imagem do repositório_</b>

- `docker run -it <imagem> bash`

<b>_Listar images_</b>

- `docker images`

<b>_Remover images_</b>

- `docker rmi <nome-image>`

<b>_Listar containers em execução_</b>

- `docker ps`

<b>_Listar todos os containers_</b>

- `docker ps -a`

<b>_todo_</b>

- `docker-compose up --build`

<b>_Roda a aplicação_</b>

- `docker-compose up`

<b>_Inspecionar images_</b>

- `docker inspect <nome-image>`

<b>_Subir image para Docker Hub_</b>

- `docker build -t <nome-usuario>/<nome-image>:<version> .`
- `docker tag <id-image> <nome-usuario>/<nome-image>:<version>`
- `docker login`
- `docker push <nome-usuario>/<nome-image>:<version>`
