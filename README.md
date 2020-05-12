# Ubuntu + Caddy + PHP-FPM 7.2

Caddy + PHP-FPM 7.2 + Composer built on Ubuntu 18.04 (Bionic) image for Laravel and PHP Projects

## Introduction

This is a Dockerfile to build a ubuntu based container image running nginx and php-fpm 7.2.x & Composer.

### Versioning

| Docker Tag | GitHub Release | Caddy Version | PHP Version | Ubuntu Version |
|-----|-------|-----|--------|--------|
| latest | master Branch |2 | 7.2 | bionic |
| php74 | php74 Branch |2 | 7.4.3 | bionic |

## Building from source

To build from source you need to clone the git repo and run docker build:

```bash
git clone https://github.com/jniltinho/nginx-php-fpm.git
cd nginx-php-fpm
```

followed by

```bash
docker build --no-cache -t nginx-php-fpm:latest . # PHP 7.2.x
```

or

```bash
docker build --no-cache -t nginx-php-fpm:php74 . # PHP 7.2.x
```

## Pulling from Docker Hub

```bash
docker pull jniltinho/nginx-php-fpm:latest
```

## Running

To run the container:

```bash
docker run --rm -it -v $(pwd):/app composer create-project --prefer-dist laravel/laravel app
cd app
docker run -p 8080:80 -v $(pwd):/var/www/app jniltinho/nginx-php-fpm
## docker run --rm -it -p 8080:80 -v $(pwd):/var/www/app jniltinho/nginx-php-fpm /bin/bash
```

Default web root:

```bash
/var/www/app/public
```
