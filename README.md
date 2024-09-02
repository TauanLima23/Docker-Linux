# Guia de Instalação do Docker no Ubuntu

## 1. Acesse sua VPS

Primeiro, você precisa se conectar ao servidor VPS ou Servidor Linux usando SSH.

## 2. Atualize seu Sistema

O sistema precisa ser atualizado para garantir mais segurança e confiabilidade na instalação do Docker. Execute os comandos abaixo:

```bash
sudo apt update
sudo apt upgrade
```
## 3. Instale Pacotes de Pré-requisitos

```bash
sudo apt-get install curl apt-transport-https ca-certificates software-properties-common
```
Para melhor entender o comando acima, aqui está uma curta descrição do que ele significa:

* apt-transport-https – permite que o gerenciador de pacotes transfira os tiles e os dados através de https
* ca-certificates – permite que o navegador da web e o sistema verifiquem certificados de segurança
* curl – transfere dados
* software-properties-common – adiciona scripts para gerenciar o software

## 4. Adicione a chave GPG do Docker

### 1. Primeiro, você adiciona uma chave GPG, inserindo o comando a seguir na linha de comando do sistema:

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

### 2. Adicione o repositório do Docker

```bash
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

### 3. Atualize as informações do repositório

```bash
sudo apt update
```

### 4. Verifique se a instalação será feita a partir do repositório do Docker

```bash
apt-cache policy docker-ce
```
A saída correta deve ser semelhante a esta:

```bash
docker-ce:
   Installed: (none)
   Candidate: 16.04.1~ce~4-0~ubuntu
   Version table:
       16.04.1~ce~4-0~ubuntu 500
            500 https://download.docker.com/linux/ubuntubionic/stableamd64packages
```

## 5. Instalar Docker Ubuntu

```bash
sudo apt install docker-ce
```

## 6. Verificar Status do Docker

```bash
sudo systemctl status docker
```

> ***Teste:*** Como o Docker já foi instalado, tudo o que você precisa agora é usar a imagem de teste para verificar se tudo está funcionando como deveria. Faça isso usando o comando:

```bash
sudo docker run hello-world
```


> ***Fonte:*** Hostinger Tutoriais, Andrei L., 02/09/2024
