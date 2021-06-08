# A time-tracker app

# Quick Start

1. `make init`
2. `make up`
3. Default ports are random (47001-47999) for every created project, so click the link generated in CLI with the output of `make up` command and enjoy!

You also can set desired ports for Nginx and PostgreSQL manually in generated /.env file (don't forget to run `make restart` afterwards).

## Configuring Xdebug settings for PhpStorm IDE

To integrate Xdebug with PhpStorm within a created project you need to do the following:
1. Create a PHP interpreter in the `Settings -> Languages & Frameworks -> PHP` tab from the php-fpm container in the project; make sure that Xdebug works properly in the container.
2. Type the port number `9009` at the menu `Settings -> Languages & Frameworks -> PHP -> Debug -> Xdebug -> Debug`.
3. Create a server named `Docker` in the menu `Settings -> Languages & Frameworks -> PHP -> Servers` (it matches with the value of the `ServerName` field in the IDE config for both interpreters).
4. If necessary, make proper mappings in the PHP interpreter `Settings -> Languages & Frameworks -> PHP -> Path Mappings`,
5. Click the button `Listen for PHP debug connections`; if you have any questions, please read the [documentation](https://www.jetbrains.com/help/phpstorm/debugging-with-phpstorm-ultimate-guide.html).

# Useful makefile commands

1. `make console` - default shell is zsh with preinstalled set of [plugins](https://github.com/ddlzz/symfony5-docker-website-skeleton/blob/main/docker/dev/php-cli/.zshrc)
2. `make test` - PHPUnit tests
3. `make cs` - PHP CS-fixer with predefined [rule sets](https://github.com/ddlzz/symfony5-docker-website-skeleton/blob/main/app/.php_cs.dist) 
4. `make psalm` - Psalm (default level is 1)

