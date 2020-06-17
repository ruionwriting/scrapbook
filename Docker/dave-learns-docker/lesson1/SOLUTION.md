# Lesson 1 solution

Dave will get an error like this one:

```shell
$ docker-compose up
ERROR:
        Can't find a suitable configuration file in this directory or any
        parent. Are you in the right directory?

        Supported filenames: docker-compose.yml, docker-compose.yaml

```

## Why

The output is self-explanatory `docker-compose up` expects files named in a specific way. If any of the know files are present it will.

> It will be convenient in various scenarios to have multiple Compose files. Dave will learn his ways.

We can get around this in 2 ways.

1st running `docker-compose` like this `docker-compose -f <compose file> up`:

```shell
$ docker-compose -f docker-compose.dev.yml up
Creating network "lesson1_default" with the default driver
Creating lesson1_web_1 ... done
Attaching to lesson1_web_1
lesson1_web_1 exited with code 0
```

2nd you can use a special environment variable known to Compose, `COMPOSE_FILE`:

```shell
$ COMPOSE_FILE=docker-compose.dev.yml docker-compose up
Starting lesson1_web_1 ... done
Attaching to lesson1_web_1
lesson1_web_1 exited with code 0
```

Same result and Dave is super happy that he nailed this one.

## Learning more

Dave also went and did a Google search and found this amazing guide about [Compose CLI environment variables](https://docs.docker.com/compose/reference/envvars/#:~:text=COMPOSE_FILE,by%20that%20name%20is%20found.). He learned there a good number of other variables he can set to control Compose execution behaviour.

Well done Dave.

[Lesson 2](../lesson2/README.md)
