# Lesson 3

Excited with previous learnings Dave goes all crazy and starts to like this Compose thing.

He created the _.env_ file than changed it a bit:

```shell
TAG=latest

```

All because he learned that he could use additional features on Compose.

Dave now has the following _docker-compose.yml_:

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

He's now using **env_file** and **environment** to explore the behaviour of environment variables order/precedence. He also created a _Dockerfile_ and an entrypoint script. Why not? He knows a log about Docker and Compose by now. Will that `command` instruction confuse Dave and/or make things work in a way he didn't anticipated?

The _Dockerfile_:

```docker
FROM alpine:latest

COPY entrypoint.sh ./
ENTRYPOINT ["sh", "/entrypoint.sh"]

```

_entrypoint.sh_ looks like this (Dave doesn't know to much about Bash, don't judge him please):

```bash
echo "Welcome ${LAST_NAME}, ${FIRST_NAME}"

```

_dev.env_ looks like this:

```shell
FIRST_NAME=Dave
LAST_NAME=Happy

```

Because Dave now uses a _Dockerfile_ he already knows that `docker-compose up` by itself is not sufficient to get the ball rolling, now there is a Docker image that will build.

What do you think will happen whe Dave runs `docker-compose up --build`?
What you think the output will be for fist name and last name?

Read the solution [here](SOLUTION.md).
