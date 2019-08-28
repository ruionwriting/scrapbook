# Docker Cheat-Sheet

## `docker run` examples

> For any dedails refer to the official [Docker run reference](https://docs.docker.com/engine/reference/run/).

The following example runs a local image `my-service-image:dev` and

- Maps local port (using `-p` option) `8443` with container exposed port `8443`
- Set environment variables using `example.env` via `--env-file` option
- Set the name of the container to `my-service` using the `--name` option
- Define a volume with `-v` option mapping a local `$PKI_PATH` with the containers `/etc/pki`

```bash
docker run --rm -it -p 8443:8443 \
  --env-file default.env \
  --name my-service \
  -v $PKI_PATH:/etc/pki \
  my-service-image:dev
```

## How-To

- [Handling File Permissions When Writing to Volumes from #Docker Containers](https://dille.name/blog/2018/07/16/handling-file-permissions-when-writing-to-volumes-from-docker-containers/)
- [Run multiple services in a container](https://docs.docker.com/config/containers/multi-service_container/)
