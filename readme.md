Insert in secrets your PRIVATE KEY for deploy key

<div align="center">

# Laravel Deploy

[![ForTheBadge built-with-love](http://ForTheBadge.com/images/badges/built-with-love.svg)](https://ngocquyhoang.com)
[![forthebadge](https://forthebadge.com/images/badges/contains-cat-gifs.svg)](https://ngocquyhoang.com)
[![forthebadge](https://forthebadge.com/images/badges/powered-by-water.svg)](https://ngocquyhoang.com)

</div>


## Config example:

```
name: Build and Deploy
on:
    push:
        branches:
            -   master

jobs:
    build:
        name: Build and Deploy
        runs-on: ubuntu-latest
        steps:
            -   name: Checkout Repository
                uses: actions/checkout@master
            -   name: Setup Enviroment
                uses: shivammathur/setup-php@v2
                with:
                    php-version: '8.1'
            -   name: Install Packages
                run: composer install --no-dev
            -   name: Deploy to Server
                uses: apboro/deploy@laravel
                with:
                    user: user
                    host: host
                    port: port
                    path: path
                    owner: owner
                env:
                    DEPLOY_KEY: ${{ secrets.DEPLOY_KEY }}
```
