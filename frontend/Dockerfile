# Use NodeJS base image
FROM node:12 as ionic

# Create app directory in Docker
WORKDIR /usr/src/app

# Install app dependencies by copying package.json and package-lock.json
COPY package*.json ./

# Install dependencies in Docker
RUN npm install -g ionic
RUN npm install

# Copy app from local environment into the Docker image
COPY . .

# Build application
RUN ionic build

## Run application
FROM nginx:alpine
COPY --from=ionic  /usr/src/app/www /usr/share/nginx/html
