# Lesson 2 solution

Dave will get an error like this one:

```shell
$ docker-compose up
WARNING: The TAG variable is not set. Defaulting to a blank string.
ERROR: no such image: alpine:: invalid reference format
```

## Why

Going back to Dave's compose file

```docker
version: '3'
services:
  web:
    image: alpine:${TAG}

```

we can see that Dave wants to use an environment variable `TAG` but he simply forgot to set it.

He quickly understands his mistake:

```shell
$ TAG=latest docker-compose up
Creating lesson2_web_1 ... done
Attaching to lesson2_web_1
lesson2_web_1 exited with code 0
```

## Learning more

Dave discovered a great document on [Environment variables in Compose](https://docs.docker.com/compose/environment-variables/) and discovered a really nice way to test his compose files in advance:

```shell
$ docker-compose config
WARNING: The TAG variable is not set. Defaulting to a blank string.
services:
  web:
    image: 'alpine:'
version: '3.0'
```

He thought to himself "this is cool".

On that same document dave also discovered that Compose supports a **.env file** that can be used to set some environment variables for his Compose files to use.

He created the _.env_ file like this:

```shell
TAG=latest
```

And everything worked. Dave started to see the potential of it right away.

[Lesson 3](../lesson3/README.md)