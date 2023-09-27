# laravel-sail-installer
📦 Revive the old `laravel new` syntax for project initialization
while taking advantage of Laravel's built-in containerizing solution, a.k.a **Laravel Sail**.

## Setup
To start using the command line tool you will need to clone this repository and run the `setup.sh` script:

```bash
git clone https://github.com/IvoKara/laravel-sail-installer.git
cd laravel-sail-installer
./setup.sh
```

This step copies the `laravel-sail-installer.sh` to your `~/.local/bin` directory 
under the name `laravel` making it accessible for the _current user only_.

If you prefer to make it accessible for the whole system you can manually move the 
installer script to `/usr/local/bin` (root privileges needed).

**After this you are ready to go!**

## Usage 

To create your conteinerized Laravel project with Sail simply type:

```bash
laravel new example-app
```

Of course, instead of "example-app" you can type whatever you want as an application name - just make sure 
it only contains alpha-numeric characters, dashes, and underscores. 
The Laravel application's directory will be created within the directory you execute the command from.


### Choose your sail service
Additionally you can specify which of the services should be included in your application.

As per [Laravel's documentation](https://laravel.com/docs/10.x#choosing-your-sail-services) currently available services are:
 * `mysql`
 * `pgsql`
 * `mariadb`
 * `redis`
 * `memcached`
 * `meilisearch`
 * `minio`
 * `selenium`
 * `mailpit`

If you do not specyfy any of them the default configuration stack 
will include `mysql`, `redis`, `meilisearch`, `mailpit`, and `selenium`.

For example you just need `mysql` and `redis` so you will need to type:
```bash
laravel new example-app -w mysql,redis
```
or alternatively
```bash
laravel new example-app --with="mysql,redis"
```

> Disclamer: you can pass the `-w` or `--with` flag before or after the application's name

You might also like to install a default [Devcontainer](https://laravel.com/docs/10.x/sail#using-devcontainers) 
by typing `devcontainer` instead of the `new` keyword:
```bash
laravel devcontainer example-app --with="mysql,redis"
```
