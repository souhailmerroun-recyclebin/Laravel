# Steps

1/
```
git clone https://github.com/souhailmerroun/laravel-with-docker.git
```

2/
```
docker run --rm -v $(pwd):/app composer create-project --prefer-dist laravel/laravel laravel
```

PowerShell Windows 10
```
docker run --rm -v "$(pwd):/app" composer create-project --prefer-dist laravel/laravel laravel
```

3/
Move the content of the ``laravel` folder into the root `./`

4/
```
docker-compose build
docker-compose up
```

5/ 
If there are no .env, clone .env.example, run these commands then rebuild docker-compose and run it
```
docker-compose exec app php artisan key:generate
```

6/
Normally, the Laravel app should be running on localhost and a MySQL connexion is should be available at 
```
DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=mydatabase
DB_USERNAME=root
DB_PASSWORD=mypassword
```

To understand DB_HOST, checking the common issues down below. 
You should be able to run the migrations to test the db connexion with MySQL. 
```
docker-compose exec app php artisan migrate
```

7/
To run phpunit:
```
docker-compose exec app ./vendor/bin/phpunit
```

Common Issues:
While trying to connect to MySQL database, two issues might come up:
- [Using Docker I get the error: “SQLSTATE[HY000] [2002] No such file or directory”](https://stackoverflow.com/questions/40075065/using-docker-i-get-the-error-sqlstatehy000-2002-no-such-file-or-directory)
- [Laravel SQLSTATE[HY000] [2002] Connection refused
](https://stackoverflow.com/questions/41225720/laravel-sqlstatehy000-2002-connection-refused)

Source: 
- [How To Set Up Laravel, Nginx, and MySQL with Docker Compose
](https://www.digitalocean.com/community/tutorials/how-to-set-up-laravel-nginx-and-mysql-with-docker-compose)
- [E: Package 'mysql-client' has no installation candidate in php-fpm image build using docker compose
](https://stackoverflow.com/questions/57048428/e-package-mysql-client-has-no-installation-candidate-in-php-fpm-image-build-u)
