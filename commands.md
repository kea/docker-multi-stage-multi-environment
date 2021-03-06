List of all commands unsed during the live demo

# Part 1

docker run debian ls
docker run --rm debian ls
docker run --rm -it debian bash

alias 

drun php -v
drun node node -v
drun golang go version

drunv php php date.php
drunv node node date.js
drunv golang go run date.go

drunv -p 80:80 php -S 0.0.0.0:80

# Part 2

## Official PHP

docker build . -f Dockerfile-php -t phpday:php

drunv -p 80:80 phpday:php

drun phpday:php ./vendor/bin/phpunit
drunv phpday:php composer install
drunv phpday:php ./vendor/bin/phpunit

drun phpday:php php -m

## Official PHP Multi-stage

docker build . -t phpday:php-multi
docker build . -t phpday:php-multi-cli --target cli
drunv phpday:php-multi-cli ./vendor/bin/phpunit
drunv phpday:php-multi-cli ./artisan
drunv -p 80:80 phpday:php-multi

# Alpine Multi-stage

docker-compose build

docker-compose up app

docker-compose run cli ./artisan

# Part 3

scar ls

docker-compose build

docker save 245004962504.dkr.ecr.us-east-1.amazonaws.com/phpday:artisan | gzip -c > phpday.tar.gz

drunv -v /root/.aws:/home/scar/.aws -v /root/.scar/:/home/scar/.scar grycap/scar

cd part3/application/

pip3 install --upgrade scar --user

scar init -f scar.yaml

scar run -f scar.yaml ./artisan phpday:date

scar run -f scar.yaml ./artisan phpday:route date

scar invoke -f scar.yaml -p '{"API_ROUTE":"/api/date"}'
