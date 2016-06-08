# Base image ubuntu
FROM    ubuntu

# Instalar dependencias

RUN apt-get update
RUN apt-get -y install sudo
RUN apt-get -y install curl
RUN curl -sL https://deb.nodesource.com/setup | sudo bash -
RUN apt-get -y install python build-essential nodejs

# Instalar nodemon
RUN npm install -g nodemon

# Provides cached layer for node_modules
ADD package.json /tmp/package.json
RUN cd /tmp && npm install
RUN mkdir -p /src && cp -a /tmp/node_modules /src/

# Working directory
WORKDIR /src
ADD . /src

# Expose port
EXPOSE  8080

# Run app using nodemon
CMD ["nodemon", "/src/index.js"]
