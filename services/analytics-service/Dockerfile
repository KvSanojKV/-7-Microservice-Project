FROM php:8.3-cli

WORKDIR /app

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    libpq-dev \
    && docker-php-ext-install pdo_pgsql \
    && rm -rf /var/lib/apt/lists/*

COPY . .

EXPOSE 8087

CMD ["php", "-S", "0.0.0.0:8087", "router.php"]
