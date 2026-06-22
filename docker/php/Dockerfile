FROM php:8.3-fpm

# 1. Install dependencies sistem
RUN apt-get update && apt-get install -y \
    git \
    unzip \
    zip \
    libzip-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# 2. Install ekstensi PHP
RUN docker-php-ext-install pdo_mysql zip

# 3. Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# 4. Set working directory
WORKDIR /var/www