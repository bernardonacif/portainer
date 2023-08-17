### README.md (Português)

# Inicialização do Container Portainer usando Docker Compose

## Introdução

Este guia fornecerá instruções passo a passo para a inicialização de um container Portainer usando o Docker Compose, que é uma ferramenta para definir e executar aplicativos Docker multi-container. O Portainer oferece uma interface amigável para gerenciar seus ambientes de contêineres.

## Pré-requisitos

Antes de começar, certifique-se de ter o Docker e o Docker Compose instalados em sua máquina. Você pode baixá-los em [Docker Website](https://www.docker.com/get-started) e [Docker Compose](https://docs.docker.com/compose/install/).

## Passo a Passo

1. Crie um arquivo chamado `docker-compose.yml` em um diretório de sua escolha.

2. Abra o arquivo `docker-compose.yml` em um editor de texto e adicione o seguinte conteúdo:

```yaml
version: '3'
services:
  portainer:
    image: portainer/portainer-ce
    container_name: portainer
    ports:
      - "9000:9000"
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - portainer_data:/data
    restart: always

volumes:
  portainer_data:
```

3. Salve o arquivo `docker-compose.yml`.

4. Abra um terminal ou prompt de comando.

5. Navegue até o diretório onde você criou o arquivo `docker-compose.yml`.

6. Execute o seguinte comando para iniciar o container Portainer:

```bash
docker-compose up -d
```

7. O Portainer estará disponível em seu navegador em `http://localhost:9000`.

8. Na primeira execução, você precisará definir uma senha de administrador.

9. Escolha o ambiente Docker que deseja gerenciar (local ou remoto).

10. Parabéns! Agora você está pronto para começar a gerenciar seus contêineres usando o Portainer.

### README.md (English)

# Initializing Portainer Container Using Docker Compose

## Introduction

This guide will provide step-by-step instructions to initialize a Portainer container using Docker Compose, which is a tool for defining and running multi-container Docker applications. Portainer offers a user-friendly interface to manage your container environments.

## Prerequisites

Before you begin, make sure you have Docker and Docker Compose installed on your machine. You can download them from [Docker Website](https://www.docker.com/get-started) and [Docker Compose](https://docs.docker.com/compose/install/).

## Step by Step

1. Create a file named `docker-compose.yml` in a directory of your choice.

2. Open the `docker-compose.yml` file in a text editor and add the following content:

```yaml
version: '3'
services:
  portainer:
    image: portainer/portainer-ce
    container_name: portainer
    ports:
      - "9000:9000"
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - portainer_data:/data
    restart: always

volumes:
  portainer_data:
```

3. Save the `docker-compose.yml` file.

4. Open a terminal or command prompt.

5. Navigate to the directory where you created the `docker-compose.yml` file.

6. Run the following command to start the Portainer container:

```bash
docker-compose up -d
```

7. Portainer will be available in your browser at `http://localhost:9000`.

8. On first run, you'll need to set an administrator password.

9. Choose the Docker environment you want to manage (local or remote).

10. Congratulations! You are now ready to start managing your containers using Portainer.

