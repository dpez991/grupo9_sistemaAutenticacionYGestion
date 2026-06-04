FROM mcr.microsoft.com/devcontainers/php:1-8.2-bullseye

# Quitar repo de Yarn que está rompiendo apt
RUN rm -f /etc/apt/sources.list.d/yarn.list

# Instalar MariaDB client
RUN apt-get update \
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y mariadb-client \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

# Instalar drivers de MySQL para PHP
RUN docker-php-ext-install mysqli pdo pdo_mysql