FROM php:8.2-cli

# Install system dependencies
RUN apt-get update && apt-get install -y \
    zip unzip curl git \
    && docker-php-ext-install pdo pdo_mysql 


RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Create working directory
WORKDIR /var/www

# Install Laravel installer
RUN composer global require laravel/installer \
    && echo 'export PATH="$HOME/.composer/vendor/bin:$PATH"' >> ~/.bashrc

# Create Laravel project automatically
RUN /root/.composer/vendor/bin/laravel new backend

# Set working directory to the Laravel project
WORKDIR /var/www/backend

# Install dependencies
RUN composer install

# Expose Laravel port
EXPOSE 8000

# Run Laravel server
CMD ["php", "artisan", "serve", "--host=0.0.0.0"]
