# Lesson 3 solution

Dave is happy it all worked, well almost all worked:

```shell
$ docker-compose up --build
WARNING: The LAST_NAME variable is not set. Defaulting to a blank string.
WARNING: The FIRST_NAME variable is not set. Defaulting to a blank string.
Building web
Step 1/3 : FROM alpine:latest
 ---> a24bb4013296
Step 2/3 : COPY entrypoint.sh ./
 ---> Using cache
 ---> fcbfdad7f2b5
Step 3/3 : ENTRYPOINT ["sh", "/entrypoint.sh"]
 ---> Using cache
 ---> 9ba6d5381b7e
Successfully built 9ba6d5381b7e
Successfully tagged lesson3_web:latest
Recreating lesson3_web_1 ... done
Attaching to lesson3_web_1
web_1  | Welcome Super Happy, Dave
lesson3_web_1 exited with code 0
```

Dave was not expecting to see those warnings neither he expected that command wouldn't do anything.

## Why

Going back to Dave's compose file

```docker
version: '3'
services:
  web:
    build:
      context: .
    env_file:
      - ./dev.env
    environment:
      - LAST_NAME=Super Happy
    command: sh -c "echo \"Welcome ${LAST_NAME}, $FIRST_NAME\" && echo $LAST_NAME && env"

```

Like Dave discovered that when you set the same environment variable in multiple files, the priority used by Compose to choose which value to use follows a certain rules. We went back to read a bit more in the docs.

TL;DR; when you run the container, the environment variable defined in the Compose file takes precedence - over **env_file** defined variables - hence `LAST_NAME` used was `Super Happy` not `Happy` as set in _dev.env_.

How about the **command** thing? What happened with it?

## Learning more

Well Dave had to dig a bit more on this one. He [learned](https://docs.docker.com/compose/compose-file/#entrypoint) ...

In this case the **command** set in the Compose file is being "ignored". Is that 100% true? Dave later will learn - if continues to learn Docker - that there is more to it around the way entrypoints and commands operate and how he can use them.

Dave starts to realise that Docker is still fun there are a few intrinsic details that can make him loose is marbles. Dave realises that Docker and Docker Compose requires a bit of learning to master. I'm sure Dave will learn a lot more in the following lessons.
