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

If there are no .env, clone .env.example, run these commands then rebuild docker-compose and run it
```
docker-compose exec app php artisan key:generate
docker-compose exec app php artisan config:cache
```

While trying to connect to MySQL database, two issues might come up:
a. [Using Docker I get the error: “SQLSTATE[HY000] [2002] No such file or directory”](https://stackoverflow.com/questions/40075065/using-docker-i-get-the-error-sqlstatehy000-2002-no-such-file-or-directory)
b. [Laravel SQLSTATE[HY000] [2002] Connection refused
](https://stackoverflow.com/questions/41225720/laravel-sqlstatehy000-2002-connection-refused)

Source: 
1. [How To Set Up Laravel, Nginx, and MySQL with Docker Compose
](https://www.digitalocean.com/community/tutorials/how-to-set-up-laravel-nginx-and-mysql-with-docker-compose)
2. [E: Package 'mysql-client' has no installation candidate in php-fpm image build using docker compose
](https://stackoverflow.com/questions/57048428/e-package-mysql-client-has-no-installation-candidate-in-php-fpm-image-build-u)
