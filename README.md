# laravel-sail-installer
📥 Lightweight and simple Laravel + Sail project installer

## Setup
To start using the command line tool you will need to clone this repository and run the `install.sh` script

```bash
git clone
cd
./install.sh
```

And you are now ready to go!

## Usage 
The above scenario just copies the `laravel-sail-installer.sh` to your `usr/local/bin` directory 
under the name `laravel` in order to be accessible in the whole system.


To create your Laravel + Sail project simply type:

```bash
laravel new example-app
```

Of course, instead of "example-app" you can type whatever you want as an application name - just make sure 
it only contains alpha-numeric characters, dashes, and underscores. 
The Laravel application's directory will be created within the directory you execute the command from.


### Choose your sail service
Additionally you can specify which of the services sail should include in your application.
As per [Laravel's documentation](https://laravel.com/docs/10.x#choosing-your-sail-services) currently available services are
`mysql`, `pgsql`, `mariadb`, `redis`, `memcached`, `meilisearch`, `minio`, `selenium`, and `mailpit`.

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

> Disclamer: you can pass the `-w`\`--with` flag before or after the application's name

You might also like to install a default [Devcontainer](https://laravel.com/docs/10.x/sail#using-devcontainers) 
by typing `devcontainer` instead of the `new` keyword:
```
laravel devcontainer example-app --with="mysql,redis"
```
