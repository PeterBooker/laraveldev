# Laravel Dev
Docker based development environment for Laravel- Includes Caddy, MariaDB, PHP, Redis, Mailhog and Adminer.

## Dependencies

* Docker - ([windows](https://docs.docker.com/docker-for-windows/install/), [mac](https://docs.docker.com/docker-for-mac/install/))
* Docker-Compose - ([install](https://docs.docker.com/compose/install/))

## Features

Creates a full development environment for Laravel containing:

- [x] Caddy (Web Server)
- [x] MariaDB
- [x] Redis
- [x] [PHP](https://github.com/PeterBooker/docker-php) (7.3)
- [x] Mailhog
- [x] Adminer

You can easily customize this further by editing the `docker-compose.yml` file yourself.

## Usage

The easiest way to use this is by cloning it into a directory for each site you want.

`git clone https://github.com/PeterBooker/laraveldev.git dir-name`

Next, from the newly created directory, start up the Docker containers:

`docker-compose up -d`

Now you can continue as you would normally, either by symlinking your project to `./docker/html/` or setting up a new project. For convenience the PHP container has composer installed, allowing you to connect to the container `docker exec -it local_php_1 /bin/sh` and set up a new project as you would normally (the root needs to be at `/var/www/html`).

From this point you can start and stop the containers with:

`docker-compose start` and `docker-compose stop`

Finally, you can remove the containers:

`docker-compose down`

## TODO

- [ ] Replace Caddy with NGINX and Apache, switched via Environment Variable.
- [ ] Add convenience scripts for DB backups, DB imports and adding content like Theme Unit Test data.

## License

Licensed under MIT.