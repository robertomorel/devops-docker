#docker run --rm -it -v $(pwd)/:/usr/src/app -p 3000:3000 node:15 bash

FROM node:15

WORKDIR /usr/src/app

# Desnecessário para desenvolvimento
#COPY . .

RUN apt-get update && apt-get install -y wget

# Instalando o Dockerize 
# Se executar: "dockerize -wait tcp://db:3306" neste container, nós teremos:
ENV DOCKERIZE_VERSION v0.6.1
RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

EXPOSE 3000

# CMD ["node","index.js"]