# Instalando o Docker

### Documentação

_https://docs.docker.com/install/linux/docker-ce/ubuntu/_

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

## Comandos do Docker

- `docker build`
- `docker pull`
- `docker run`
