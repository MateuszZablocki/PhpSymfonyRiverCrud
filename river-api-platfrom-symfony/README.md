 River API
=======================

### 1. Requirements

- Symfony CLI version v4.13.3
- PHP 7.4.*

### 2. Clone project

```
git clone git@github.com:gajdaw-teaching/ex-03-rivers-crud.git
```

### 3. How to run API

```
Change line DATABASE_URL in .env file to match your mySQL configuration: 
DATABASE_URL=mysql://user:password@127.0.0.1:3306/db_name?serverVersion=5.7

bash
cd mateusz-zablocki
cd river-api-platform-symfony
composer install
php bin/console doctrine:database:create
php bin/console make:migration
php bin/console doctrine:migration:migrate -n
php -S 127.0.0.1:8000 -t public
```

Go to page:

[127.0.0.1:8000/](127.0.0.1:8000/)

[127.0.0.1:8000/api/](127.0.0.1:8000/api/)

### 4. Curl
[POST]

`curl -X POST "http://127.0.0.1:8000/api/rivers" -H "accept: application/ld+json" -H "Content-Type: application/ld+json" -d "{\"name\":\"Wisła\",\"length\":111}"`

[GET]

`curl -X GET "http://127.0.0.1:8000/api/rivers?page=1" -H "accept: application/ld+json"`

[PUT]

`curl -X PUT "http://127.0.0.1:8000/api/rivers/2" -H "accept: application/ld+json" -H "Content-Type: application/ld+json" -d "{\"name\":\"test\",\"length\":111}"`

[DELETE]

`curl -X DELETE "http://127.0.0.1:8000/api/rivers/1" -H "accept: */*"`

