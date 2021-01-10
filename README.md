![header](https://dvlprabhi-dp.vercel.app/?text=InstaBook)

InstaBook is a simple cloud application. It allows users to register and log into a web client, post photos to the feed.

The project is split into two parts:

1. Frontend - Angular web application built with Ionic Framework
2. Backend RESTful API - Node-Express application

### Requirements

Download and install Node from [https://nodejs.com/en/download](https://nodejs.org/en/download/)

### Environment Script

A file named `env.list` is present in root of repository. Use this to configure variables for your local development environment.

### Docker Image

#### Backend-API

1. Setup Docker on your machine.
2. Pull the public image from DockerHub using command `docker pull abhimanyudwivedi/instabook-api:latest`
3. Create a file `env.list` which contains environment variables for application.

```
$ cat > env.list
POSTGRES_USERNAME=
POSTGRES_PASSWORD=
POSTGRES_HOST=
POSTGRES_DB=
AWS_BUCKET=
AWS_REGION=
AWS_PROFILE=
JWT_SECRET=
URL=
```

4.  Run the image.

```
docker run --name instabook-api -p 8080:8080 --env-file env.list -d abhimanyudwivedi/instabook-api
```

### Database

Create a PostgreSQL database either locally or on AWS RDS. Set the config values for environment variables prefixed with `POSTGRES_` in `set_env.sh`.

### S3

Create an AWS S3 bucket. Set the config values for environment variables prefixed with `AWS_` in `set_env.sh`.

### Back-end API

- To download all the package dependencies, run the command from the directory `api/`:
  ```bash
  npm install .
  ```
- To run the application locally, run:
  ```bash
  npm run dev
  ```

### Front-end App

- To download all the package dependencies, run the command from the directory `frontend/`:
  ```bash
  npm install .
  ```
- Install Ionic Framework's Command Line tools for us to build and run the application:
  ```bash
  npm install -g ionic
  ```
- Prepare your application by compiling them into static files.
  ```bash
  ionic build
  ```
- Run the application locally using files created from the `ionic build` command.
  `bash ionic serve `
  You can visit `http://localhost:8100` in your web browser to verify that the application is running. You should see a web interface.

  ***

If you liked Dynamic Text Header used in this README, check it out [here](https://gist.github.com/dwivediabhimanyu/f7f11956abc3ebd8015a668834c3d6c0) .
