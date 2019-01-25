# 📰 docker-compose-wordpress

> Ready-to-use Docker + WordPress 5 repository

## Goal

This repository aims at providing a way to start developing websites, themes or plugins on [Wordpress](https://wordpress.org/) 5 using the latest stable needed dependencies.

It's also a fast way to launch a demo WordPress website and test anything you want on it.

## Requirements

- [Docker](https://docs.docker.com/install/)

## How to use

```sh
wget https://github.com/algolia/docker-compose-wordpress/archive/master.zip -O tmp-master-docker-compose.zip
unzip tmp-master-docker-compose.zip
rm tmp-master-docker-compose.zip
mv docker-compose-wordpress-master super-blog
cd super-blog
wget https://wordpress.org/latest.zip
unzip latest.zip
rm latest.zip
docker-compose up
```

Then:
- open http://localhost:44000/
- Choose the installation language for WordPress
- At the database configuration step, just change `localhost` to `db`:

![Database step](/additional-configurations/database-step.png)

Then follow the WordPress installation instructions.

## If something goes wrong

```sh
rm -rf db
docker-compose stop
docker-compose rm
docker-compose up
```

## Stack

From reading the [docker-compose.yml](./docker-compose.yml) file:
- [MariaDB](https://mariadb.org/):10.3.12, data is stored in `./db/`
- [NGINX](https://nginx.org/):1.15.8
- [Adminer](https://www.adminer.org/):4.7.1. For observing the database
- [PHP FPM](http://php.net/manual/fr/install.fpm.php):7.3.1
- `./wordpress/` will hold your wordpress installation once you follow [How to use](#how-to-use)

## Credentials

You can connect to the database by using:
- http://localhost:44100
- *System*: MySQL
- *Server*: db
- *Username*: username
- *Password*: password
- Leave *Database* empty

Or any other GUI client, like [TablePlus](https://tableplus.io/).
