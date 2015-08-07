# Heroku Buildpack: Make

Use this buildpack to run any code in a `heroku` Makefile target:

## Usage

Add the `heroku` target to your Makefile:

```Makefile

heroku:
  @echo 'Working ...'

.PHONY: heroku

```

Then use [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) to use the buildpack: 

    $ heroku create myapp_name -s cedar
    $ heroku buildpacks:set https://github.com/ddollar/heroku-buildpack-multi.git
    $ echo "https://github.com/other-build-pack.git" >> .buildpacks
    $ echo "https://github.com/kelonye/heroku-buildpack-make.git" >> .buildpacks
    $ git push heroku master
