AS docker - Symfony (flex)
========================
implement Docker into your Symfony (^4.0) project using flex


Requirements
---
 * configure your local [projects enrironment](https://bitbucket.org/as-docker/projects-environment)
 * [optional] install composer globally [global composer command](https://hub.docker.com/r/amsdard/composer/)
 * make sure You have [YAKE](https://yake.amsdard.io/) installed
 * symfony ^4.0 with flex and basic components (see Full sample) installed


Install (when you have already an existing project)
---
In your project directory, download the package by composer (or git clone to your `~/Projects` directory)
```
composer require amsdard/symfony-as-docker
```

 * php+nginx mode (default)
```
./vendor/amsdard/symfony-as-docker/setup
```

 * apache mode
```
./vendor/amsdard/symfony-as-docker/setup apache
```
in case of `apache` mode, You may also need:
```
composer require symfony/apache-pack
```


Install - Full sample (when you install a new project)
---
In your `~/Projects` directory, create a new project (a new `my_project` directory will be created)
```
composer create-project symfony/skeleton my_project
```

Go to your `~/Projects/my_project` and run the following command to allow using a community contrib
```
composer config extra.symfony.allow-contrib true
```

install basic Symfony components
```
composer require annotations validator encore asset translator security debug-pack make
```

install as-docker
```
composer require amsdard/symfony-as-docker
./vendor/amsdard/symfony-as-docker/setup
```

run the project
```
yake yarn install
yake configure
yake up
```
now you can run `yake console make:controller Home` and go to `http://my_project.test/home`

How it works
---
* below file structure will be installed
```
.
├── README.md
├── docker-compose.yml
├── Yakefile
├── deploy
│   ├── prod
│   │   └── docker-compose.yml
│   └── rancher
│       └── docker-compose.yml
└── docker
    ├── mysql
    │   ├── config.env
    │   └── config.env.dist
    ├── nginx
    │   ├── Dockerfile
    │   └── default.conf
    └── php
        └── Dockerfile
```
* your project directory name will be filled as local domain name and docker image namespace (see `docker-compose.yml`)
* new rules will be added to your `.gitignore` file: 
  * `/composer.phar` internal project composer
  * `/docker/*/*.env` container ENV
 
