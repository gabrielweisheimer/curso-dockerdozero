Mão na massa - "Disponibilizando stack em microserviço usando Compose"

#1 - Caso ainda não tenho feito, clone meu repositório público com todos os materiais utilizados nos meus cursos ministrados na Udemy:

git clone https://github.com/ricardoferreiracosta08/cursos-udemy.git

#2 - Navegue em:

/curso-dockerdozero/secao10-DockerCompose/example-voting-app/

#3 - Nesse diretório tem uma app de exemplo de microserviços configurada para compose. Sua stack é arquitetada da seguinte maneira:

![image](https://user-images.githubusercontent.com/102634295/163898632-b92ec449-64b8-475c-be4b-62b7ede1891e.png)

##Em resumo, essa app é:

    Um aplicativo Web front-end em Python (Linux) ou ASP.NET Core (Windows) que permite votar entre duas opções (porta 5000)

    Uma fila DB NoSQL Redis (Linux) ou NATS que coleta novos votos

    Um worker do .NET Core, Java ou .NET Core 2.1 que consome votos e os armazena em…

    Um banco de dados Postgres ou TiDB persistido por um volume Docker

    Um aplicativo web Node.js ou ASP.NET Core SignalR que mostra os resultados da votação em tempo real (porta 5001)

#4 - Para vê em execução, dentro desse diretório, execute o compose para Linux

docker-compose -f docker-compose.yml up

#5 - Caso queira para Windows, execute:

docker-compose -f docker-compose-windows.yml up

#6 - No browser, acesse http://localhost:5000 para "votação" e http://localhost:5001 para "resultado"


Forked
=========

Repositório Orginal: [https://www.docker.com/products/docker-desktop](https://github.com/dockersamples/example-voting-app)
