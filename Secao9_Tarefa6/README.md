Para um provisionamento de um Repositório Online de Arquivos usando o Owncloud, com conexão a uma base de dados MySQL, os comandos Docker podem ser usados.

A fim de obter melhor entendimento sobre a manipulação do arquivo de configuração do compose, essa tarefa requer que você, a partir dos comandos docker abaixo, transcreva-os para um arquivo yml e crie um projeto Docker Compose:


    docker network create net-backend 

    docker run --name mysql --restart=always --network=net-backend 
    -v /home/data:/var/lib/mysql 
    -v /etc/localtime:/etc/localtime:ro 
    -e MYSQL_ROOT_PASSWORD=pass -d mysql:5.5 

    docker run --name owncloud --restart=always --network=net-backend 
    -p 9090:80 -v /home/apps:/var/www/html/apps 
    -v /home/config:/var/www/html/config 
    -v /home/data:/var/www/html/data 
    -v /etc/localtime:/etc/localtime:ro -d owncloud

# Perguntas dessa tarefa

## 1.# Qual conteúdo de arquivo de configuração Docker Compose melhor pode representar o o cenário apresentado?

## 2.# Após a entrega do serviço, quais valores dos parâmetros, para conexão com a base MySQL, devem ser utilizados na configuração/instalação do Owncloud:

- Usuário de banco de dados
    R: root
- Senha de banco de dados
    R: pass
- Nome do banco de dados
    R: mysql
- Host do banco de dados
    R: mysql:3306