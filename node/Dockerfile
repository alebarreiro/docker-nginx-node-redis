# Base image ubuntu
FROM    node:argon

# Create app directory
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

# Install all dependencies
COPY package.json /usr/src/app/
RUN npm install

# Bundle app source code
COPY . /usr/src/app

# Expose port
EXPOSE  8080

# Run app using nodemon
CMD ["node", "/src/index.js"]
