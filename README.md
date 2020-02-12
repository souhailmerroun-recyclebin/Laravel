# Steps

1/
```
git clone this repo
```

2/
```
docker run --rm -v $(pwd):/app composer create-project --prefer-dist laravel/laravel .
```

Warning for Powershell, use: `"$(pwd):/app"`

3/
```
docker-compose build
docker-compose up
```

4/
```
docker-compose exec app php artisan key:generate
docker-compose exec app php artisan config:cache
```

Source: 
1. [How To Set Up Laravel, Nginx, and MySQL with Docker Compose
](https://www.digitalocean.com/community/tutorials/how-to-set-up-laravel-nginx-and-mysql-with-docker-compose)
2. [E: Package 'mysql-client' has no installation candidate in php-fpm image build using docker compose
](https://stackoverflow.com/questions/57048428/e-package-mysql-client-has-no-installation-candidate-in-php-fpm-image-build-u)
