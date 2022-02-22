TODO&CO
========

[![Codacy Badge](https://app.codacy.com/project/badge/Grade/f58c223d3a8547aeaf7dcd841ec06681)](https://www.codacy.com/gh/JasonCooke1988/P8TODO/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=JasonCooke1988/P8TODO&amp;utm_campaign=Badge_Grade)

Base du projet #8 : Améliorez un projet existant

https://openclassrooms.com/projects/ameliorer-un-projet-existant-1

P8 TODO&CO is the eighth project in my PHP / Symfony developer course with OpenClassrooms.

Codacy dashboard for the project :

https://app.codacy.com/gh/JasonCooke1988/P8TODO/dashboard?branch=master

## Installation

This project requires PHP ^8.0

Clone the repository.

In the terminal cd to project root directory.

Use the package manager [composer](https://getcomposer.org/download/) to install the projects PHP dependencies.

```bash
composer install
```

Use the package manager [npm](https://www.npmjs.com/) to install the projects JS dependencies.

```bash
npm install
```

and also to generate Webpack (Symfony Encore) files

```bash
npm run build
```

Create a .env file and define the constants (except APP and APP_SECRET), the following is an example of a full .env file:

```bash
# In all environments, the following files are loaded if they exist,
# the latter taking precedence over the former:
#
#  * .env                contains default values for the environment variables needed by the app
#  * .env.local          uncommitted file with local overrides
#  * .env.$APP_ENV       committed environment-specific defaults
#  * .env.$APP_ENV.local uncommitted environment-specific overrides
#
# Real environment variables win over .env files.
#
# DO NOT DEFINE PRODUCTION SECRETS IN THIS FILE NOR IN ANY OTHER COMMITTED FILES.
#
# Run "composer dump-env prod" to compile .env files for production use (requires symfony/flex >=1.2).
# https://symfony.com/doc/current/best_practices.html#use-environment-variables-for-infrastructure-configuration

###> symfony/framework-bundle ###
APP_ENV=dev
APP_SECRET=appsecret
###< symfony/framework-bundle ###

###> doctrine/doctrine-bundle ###
# Format described at https://www.doctrine-project.org/projects/doctrine-dbal/en/latest/reference/configuration.html#connecting-using-a-url
# IMPORTANT: You MUST configure your server version, either here or in config/packages/doctrine.yaml
#
# DATABASE_URL="sqlite:///%kernel.project_dir%/var/data.db"
# DATABASE_URL="mysql://db_user:db_password@127.0.0.1:3306/db_name?serverVersion=5.7"
DATABASE_URL="mysql://root:@127.0.0.1:3306/p8todo?serverVersion=5.7"
###< doctrine/doctrine-bundle ###

# use this to configure a traditional SMTP server
#MAILER_URL=smtp://localhost:465?encryption=ssl&auth_mode=login&username=&password=
```

You may also create a .env.test for 

##Setup

Use doctrine to create databases :
`php bin/console doctrine:databse:create`

migrate database :

`php bin/console doctrine:migrations:migrate`

and load data fixtures :

`php bin/console doctrine:fixtures:load`

## Start project

From terminal `symfony server:start`

## Structure

1. assets
2. bin
3. config
4. migrations
5. public
6. src
7. templates
8. tests
9. var


## User accounts

Two user accounts have been created with doctrine data fixtures, you can connect with these credentials :

(This is the default user assigned to unassigned tasks)
Email : anon@test.com
Pass : test

Email : test@test.com
Pass : test

Or you can create your own account.

## License
[MIT](https://choosealicense.com/licenses/mit/)