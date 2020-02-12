# Steps

1/
```
git clone this repo
```

2/
```
docker run --rm -v $(pwd):/app composer create-project --prefer-dist laravel/laravel .
```

3/
```
docker-compose build
docker-compose run
```

Source: 
1. https://www.digitalocean.com/community/tutorials/how-to-set-up-laravel-nginx-and-mysql-with-docker-compose
2. https://stackoverflow.com/questions/57048428/e-package-mysql-client-has-no-installation-candidate-in-php-fpm-image-build-u
