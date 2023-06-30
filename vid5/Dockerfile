# Build off this base image
FROM node:7

# Set up app directory
WORKDIR /usr/src/app

# Install app dependencies
# RUN ["apt-get", "update", "-y"] 
COPY package.json package.json
RUN npm install

# Bundle app source
COPY server.js server.js

# Expose the server to the host machine
EXPOSE 80

# Run this command on startup
ENTRYPOINT ["npm", "start"]