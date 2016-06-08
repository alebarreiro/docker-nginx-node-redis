# Base image ubuntu
FROM    node:argon

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
CMD ["node", "/src/index.js"]
