# Setup Symfony 4.3.1 with Docker

## Setup

Follow this procedure in order to have a Symfony project with the version 4.3.1 and the local environment setup (with Docker).

1. Clone the repository: `git clone https://github.com/rfaivre/symfony4-training.git`
2. Launch the docker: `docker-compose up -d`
    * if you have some issues with the permissions of the `var` directory, please run:
        1. `chmod -R 755 var`
        2. change the owner of the `db` directory: `sudo chown -R 999:root var/db`
        3. Once done, relaunch `docker-compose up -d`
    * normally, the `composer install` command is launched.
3. Reach the url `https://site.training.docker`
4. If everything works, you must have a page explaining that the Symfony application is now ready.

## Quick Tour

* [Symfony flex](https://symfony.com/doc/current/setup/flex.html) is installed. It allows to install and automate the installation and the setup of bundles and other Composer dependencies.

Quick explanation of the structure:

* `bin`: contains the executable (for example the symfony console or phpunit)
* `config`: contains all configuration of the application and other dependencies.
* `public`: web files like images, 
* `src`: all your logic must be here.
* `templates`: contains all your templates
* `tests`: write your tests here
* `var`: temporary files
* `vendor`: composer dependencies and bundles

## Useful tips

* Run command inside the docker: `docker-compose exec web bash`. Once connected, you can reach the symfony console.
* If you want override some environment variable, specific to your local, please create a file `.env.dev.local` (this file will not be committed). For example, if you want override the database configuration.
* The symfony console is very useful. It can be used by typing: `php bin/console`
* Run unit tests: `php bin/phpunit`
* If you use PHPStorm, please install the [Symfony plugin for PHPStorm](https://plugins.jetbrains.com/plugin/7219-symfony-support)
