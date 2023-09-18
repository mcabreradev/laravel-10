<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

### Laravel Sail: How to add executablePath in VSCode Settings

Create a file named 'php' on /usr/local/bin

```bash
sudo touch /usr/local/bin/php
```

Make it executable:

```bash

sudo chmod +x /usr/local/bin/php
```

Edit the file (with sudo) and paste this code:

```bash
path=$(printf '%s\n' "${PWD##*/}")
command="docker exec ${path}-laravel.test-1 php "$@""
echo "Running php on docker ${path}-laravel.test-1"
$command
```

Now just run, example, `php -v` inside the laravel sail project.

Run migration 
```bash
sail artisan migrate
```