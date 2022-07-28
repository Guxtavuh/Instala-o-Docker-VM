# Instação docker desktop  no Linux Ubuntu 22.04
## A instalação foi feito em uma maquina virtual usando Virtual box
### Virtual box
!["Virtualbox"](https://iconarchive.com/download/i98459/dakirby309/simply-styled/VirtualBox.ico)


    
    
    VirtualBox é um software de virtualização desenvolvido pela empresa Innotek depois comprado pela Sun Microsystems que posteriormente foi comprada pela Oracle que, como o VMware Workstation, visa criar ambientes para instalação de sistemas distintos. 

    Download for windows: 

https://www.virtualbox.org/wiki/Downloads

### Após a instalação e criação da máquina virtual
ative a opção de virtualização clicando com o botao direito e indo nas configurações de cpu
e habilitar VT-x/AMD-x aninhado


### Linux ubuntu 22.04
!["Ubuntu"](https://fosstorrents.com/img/ubuntu.png)

    Ubuntu é um sistema operacional ou sistema operativo de código aberto, construído a partir do núcleo Linux, baseado no Debian e utiliza GNOME como ambiente de desktop de sua mais recente versão com suporte de longo prazo. Esta distribuição Linux é desenvolvida pela Canonical Ltd. 


    Download ISO:

https://ubuntu.com/download/desktop/thank-you?version=22.04&architecture=amd64



### Docker 
!["Docker"] (https://external-preview.redd.it/_w6PD3pDcEhKgKBmhtVxI42Jr2DjQNn2luozVVUOfLc.jpg?auto=webp&s=bb5e31b86295c2353e40a079577ceaac7c021869)


    Docker é um conjunto de produtos de plataforma como serviço que usam virtualização de nível de sistema operacional para entregar software em pacotes chamados contêineres. Os contêineres são isolados uns dos outros e agrupam seus próprios softwares, bibliotecas e arquivos de configuração.
## Configuração e instalação de ambiente
### Pós-instalação Linux
    Após a instalação do linux ubuntu 22.04, você deve executar alguns comandos para atualizar o sistema operacional e deixa-lo preparado para a instalação do docker.

### Atualização dos pacotes
```console
$ sudo apt update
```

### Atualização do sistema
```console
$ sudo apt upgrade
```


### reniciar o sistema
```console
$ reboot
```

## Instalação do Docker desktop

    Dowload Docker for desktop:
  https://docs.docker.com/desktop/install/ubuntu/

    na pasta(diretório) download localize o arquivo docker-desktop e assim vocẽ pode instalar de duas maneiras, sendo:
    1- Clicar com o botão direito e escolher software install

    2 - Abrir o terminal e ir ate a pasta download e executar o comando de instalação:
```console
    $ sudo apt install .docker-desktop-4.10.1-amd64.deb
    (Coloque sua versão no lugar de
     "docker-desktop-4.10.1-amd64.deb")
```
### caso retorne mensagem de erro referente ao docker-ce  e/ou 
### docker-cli
execute os comandos abaxo:

```console
$ sudo apt update
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
```
Adiocionar as chaves de GPG oficiais do docker
```console
 sudo mkdir -p /etc/apt/keyrings

 curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

```

### Use  comando abaixo para carregar o repositorio de pacotes
```console


 echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null


```

### Instalação do docker engine
```console

 $ sudo apt-get update

 $ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

```

### Após  a instalação das dependencias você deve executar o comando de instalação do docker desktop
```console
    $ sudo apt install .docker-desktop-4.10.1-amd64.deb

    (Coloque sua versão no lugar de
     "docker-desktop-4.10.1-amd64.deb")
```

## Instalando a imagem e o container de mysql no docker

### Vamos usar volume nesse exemplo
crie uma pasta com o nome data_docker no home do usuario
e execute o comando abaixo
```console
docker run --name servidor-mySQL -v /var/lib/mysql:/etc/mysql/conf.d -e   MYSQL_ROOT_PASSWORD="SUA SENHA" -d --rm mysql:8.0.29
```

Agora, Abra o docker desktop e veja seu container  rodando.





