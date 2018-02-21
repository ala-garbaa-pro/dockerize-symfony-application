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
composer create-project symfony/framework-standard-edition symfony "3.4.*" -vvv

# Above command will download fresh Symfony (version 3.4.*) project in `symfony` directory
# `-vvv` flag will display a detailed output of everything that Composer is doing.
```

During the installation process, you will need to provide some missing parameters
to create parameters.yml file. Example below for reference-

```
database_host: symf_mysql
database_port: 33062
database_name: fellowship
database_user: fellowship
database_password: secret
mailer_transport: smtp
mailer_host: yoursmtp.host.net
mailer_user: null
mailer_password: null
secret: ThisTokenIsNotSoSecretChangeIt
```

:exclamation: Make sure you adjust these parameters same as in `docker-compose.yml` file.

:information_desk_person: You can always update those parameters from `symfony/config/parameters.yml` file.

Next, add symfony.dev in your /etc/hosts file.

**Then, run:**

```
$ docker-compose up --build
```

:+1: All done!! now visit your Symfony application location on the following URL: http://symfony.dev:81
