FROM node:20.10.0-alpine

ENV NODE_ENV "development"
ENV NODE_PATH "/usr/src/app/node_modules"

# Install base dependencies
RUN apk update
RUN apk add git python

# Prepare app directory
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY . .

VOLUME tmp/specs

# Start the app
ENTRYPOINT ["/usr/src/app/node_modules/dredd/bin/dredd"]
