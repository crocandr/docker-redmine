# Redmine in Docker

This is a basic Redmine stack with MySQL.

## Run

```
docker-compose up -d
```

Please wait for MySQL some minutes (1-5) and Redmine DB migration process (5-10 mins) after the first start.

## Usage

By default, the redmine available on http://<your docker host>:3000 ( example: http://192.168.56.101:3000 )
Default login: admin / admin

I recommend to use an SSL proxy (like nginx - letsencrypt combo) if you would like to run Redmine with SSL.

## Configuration

You can change some basic configuration in `configuration.yml` file.
The email configured to localhost by default, but You should change this and set your mail server.

More informations:
  - http://www.redmine.org/wiki/1/EmailConfiguration
  - https://github.com/redmine/redmine/blob/master/config/configuration.yml.example

Change the default mail settings as soon as possible (in the `configuration.yml` and on redmine web too).

## Plugins

Put the uncompressed plugin's folder into the `plugins` folder and after the restart, the Redmine will be installed automatically.

Good to know: Some complex plugin can't install automatically, You should build into the Redmine container with OS package installation and other steps.

