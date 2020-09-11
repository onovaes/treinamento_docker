# Treinamento docker

O objetivo desse curso é fornecer informações básicas sobre docker para desenvolvedores.

## Introdução

O Docker é uma plataforma de código aberto para criação de ambientes isolados via container. O funcionamento do docker é possibilitado pelo Linux container — LXC — que nada mais é do que um sistema do kernel do Linux. 

Abaixo a diferença entre os container e máquina virtual (virtual box)

![Containers X Virtualizadores](images/lxc-vm.jpg)


## Containers
Container nada mais é do que um ambiente isolado contido em um servidor que, diferentemente das máquinas virtuais, divide um único host de controle.


### Images
Images Docker são compostas por sistemas de arquivos de camadas que ficam uma sobre as outras. Ela é a nossa base para construção de uma aplicação, ela pode ser desde o base do CentOS como também um CentOS com Apache, PHP e MySQL.

### Volumes

Um volume pode ser apenas o mapeamento de pasta entre o host (seu PC) e container, bem como o mapeamento de uma pasta entre containers.

![Veja um exemplo de mapeamento entre host e container:](images/host_container-e1439675513141.jpg)


### Portas


### Comandos Básicos

    Informações do docker
    $docker info

    Listar imagens
    $docker images


### Exemplos
    
    Rodando um ubuntu
    $docker run -it ubuntu bash

### TO-DO

Lista de itens a serem incluídos no curso

- [ ] PULL E PUSH em images
- [ ] Docker Compose
