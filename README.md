# SDOH & Place Discovery App - GeoBlacklight

This is a customized implementation of [GeoBlacklight](https://geoblacklight.org). It is a Rails app that depends on Apache Solr and Postgres.

## Dev Installation

To run GeoBlacklight for development purposes, you can simply use

    bundle exec rails s

However, the dependencies must be handled before running this command, and there are a couple of ways to do this. The easiest is with [Lando](https://docs.lando.dev/getting-started/installation.html), which is configured in `.lando.yml`. By default all sections of that config are commented out, so just uncomment the sections you want, navigate to the app root directory, and then run

    lando start

Use `lando list` to see what containers lando is currently running. Use `lando poweroff` to shutdown all containers.

You don't need to use Lando--you can also connect GeoBlacklight to existing instances of these apps.

### Solr config

Set the `SOLR_URL` environment variable before starting the Rails app, and GeoBlacklight will use it to find Solr. The value should look like:

    SOLR_URL=http://<ip or domain>:8983/solr/blacklight-core

### Postgres config

All database settings are in `config/database.yml`. ***Do not commit any custom database settings to this repo***.
