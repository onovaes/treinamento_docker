# Treinamento docker

O objetivo desse curso é fornecer informações básicas de docker para desenvolvedores.

## Introdução

O Docker é uma plataforma de código aberto para criação de ambientes isolados via container. O funcionamento do docker é possibilitado pelo Linux container — LXC — que nada mais é do que um sistema do kernel do Linux. 

Abaixo a diferença entre os container e máquina virtual (virtual box)

![Containers X Virtualizadores](images/lxc-vm.jpg)

## Instalação do Docker

Instalando o docker no mac. https://docs.docker.com/docker-for-mac/install/


### Containers
Container nada mais é do que um ambiente isolado contido em um servidor que, diferentemente das máquinas virtuais, divide um único host de controle.


### Images
Images Docker são compostas por sistemas de arquivos de camadas que ficam uma sobre as outras. Ela é a nossa base para construção de uma aplicação, ela pode ser desde o base do CentOS como também um CentOS com Apache, PHP e MySQL.

### Volumes

Um volume pode ser apenas o mapeamento de pasta entre o host (seu PC) e container, bem como o mapeamento de uma pasta entre containers.

Veja um exemplo de mapeamento entre host e container

![Mapeamento entre host e container:](images/host_container-e1439675513141.jpg)


### Portas

O argumento -p permite que você direcione uma porta do host (sua máquina local) para dentro do container

### Alguns Básicos

    Informações do docker
    $docker info

    Listar imagens
    $docker images

    Buscando uma imagens
    $docker search ubuntu

    Baixando a Imagem
    $docker pull ubuntu

    Criar um container
    $docker run nome_da_imagem

    Criar um container e entrar no Terminal
    O -i significa interatividade e o -t que queremos um link com o Terminal do container.
    $docker run -it ubuntu /bin/bash

    Criar um container com um apelido
    $docker run --name ubuntinho ubuntu

    Entrando num container em execução
    $docker exec -it [container-id] bash

    Enviando comando para o container (sem entrar no container)
    $docker exec -it [container-id] ls -la

    Listar containers em execução
    $docker ps

    Listar todo os containers
    $docker ps -a

    "Stopa um container"
    $docker stop id_ou_apelido
    
    Remove um cotainer
    $docker rm id_ou_apelido

    Containers auto destrutivos. Com comando --rm, podemos montar containers que se destroem ao sairmos da sessão.
    $docker run -it --rm -p 8080:80 nginx bash

    Remove containers, networks, images e caches não usados
    $docker system prune

### Exemplos
    
    Apache e php7.4
    $docker run -d -p 80:80 -v ~/Documents/meu_site/:/var/www/html php:7.4-apache

### Alguns hacks para facilitar a vida.

    Para todos os containners
    $docker stop $(docker ps -a -q)
    
    Remove todos os containers  
    $docker rm $(docker ps -a -q)
    
    Remove todas as imagens
    $docker rmi $(docker images -q)


### TO-DO

Lista de itens a serem incluídos no curso

- [ ] Instalação do docker nos windows
- [ ] Docker Build
- [ ] Commit, PULL E PUSH em images
- [ ] Networks
- [ ] Docker Compose
- [ ] Dockerfile
- [ ] DockeSwarm

### Instalação no windows

Este procedimento de instalação são para as versões windows 10 pro ou superiores que
atendam as especificações e requisitos de sistema descritos abaixo.

**********
Requisitos
**********

-  `Windows 10 64 bits: Pro, Enterprise ou Education (Build 16299 ou posterior).`
-  `For Windows 10 Home, see Install Docker Desktop on [Windows Home](https://docs.docker.com/docker-for-windows/install-windows-home/)`
-  `Hyper-V e containers precisam estar habilitados.`

Para habilitar o hyper-v no windows, basta ir no menu iniciar e pesquisar por recursos do windows.
Após isso será necessário abrir o aplicativo de recursos. Portanto, com a janela aberta procure Hyper-V e habilite
esta opção.

![image](https://user-images.githubusercontent.com/26008720/94700839-efefef00-0309-11eb-9114-6ed926ec3040.png)

## Install Docker Desktop on Windows

-  `Clique duas vezes em Docker Desktop Installer.exe para executar o instalador.`
-  `Se você ainda não baixou o instalador (Docker Desktop Installer.exe), pode obtê-lo no [Docker Hub](https://hub.docker.com/_/docker).`
-  `Quando solicitado, certifique-se de que a opção Ativar recursos do Windows do Hyper-V esteja selecionada na página Configuração.`
-  `Siga as instruções do assistente de instalação para autorizar o instalador e continue com a instalação.`
-  `Quando a instalação for bem-sucedida, clique em Fechar para concluir o processo de instalação.`
-  `Se sua conta de administrador for diferente de sua conta de usuário, você deve adicionar o usuário ao grupo docker-users. Execute o Gerenciamento do computador como administrador e navegue até Usuários e grupos locais> Grupos> docker-users`

## Iniciar o docker

![docker-app-search](https://user-images.githubusercontent.com/26008720/94702510-d8196a80-030b-11eb-8a1c-f5092b4d6e3c.png)

## Verificando se a instalação do docker foi realizada com sucesso

![whale-icon-systray](https://user-images.githubusercontent.com/26008720/94702778-23cc1400-030c-11eb-83b6-47656bbc8c3a.png)

Quando a inicialização é concluída, o Docker Desktop inicia o tutorial de integração. O tutorial inclui um exercício simples para construir uma imagem Docker de exemplo, executá-la como um contêiner, enviar e salvar a imagem no Docker Hub.

![docker-tutorial-win](https://user-images.githubusercontent.com/26008720/94703005-62fa6500-030c-11eb-8c26-e18ff725f6ae.png)


