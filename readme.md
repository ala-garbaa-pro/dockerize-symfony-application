# docker-symfony

This is just a quick note for self to up and run Symfony project with Docker.

## Installation

**First, clone this repository:**

```
git clone https://github.com/dambergautam/symfony-docker.git symfony-docker
```

**Add fresh Symfony 3.4 project**

```
cd symfony-docker
git clone <url>
```

**Setup laravel project**

```
cd symfony-docker/app

# Add env file
cp .env.example .env

# Adjust your environment variables
```

Next, add symfony.dev in your /etc/hosts file.

Make sure you adjust database environment in `docker-compose.yml` same as `app/.env` file.

**Then, run:**

```
$ docker-compose up --build
```

Hurry!! now visit your Symfony application on the following URL: http://symfony.dev:8080
