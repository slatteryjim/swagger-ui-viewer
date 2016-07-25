# swagger-ui-viewer

[![Docker Pulls](https://img.shields.io/docker/pulls/slattery/swagger-ui-viewer.svg?maxAge=2592000)](https://hub.docker.com/r/slattery/swagger-ui-viewer/)

Launch a quick web UI for your swagger.json file.

## Example
Given a `swagger.json` file in the current directory (`$PWD/swagger.json`), we can launch a viewer for it using this docker image:
```bash
$ docker run --rm -p 8080:80 -v $PWD/swagger.json:/www/swagger.json slattery/swagger-ui-viewer
```
Then view the docs in your browser at: [http://localhost:8080](http://localhost:8080)

Note the port and json file are customizable, e.g. to use localhost:5000 and `/tmp/my-swagger-file.json`:
```bash
$ docker run --rm -p 5000:80 -v /tmp/my-swagger-file.json:/www/swagger.json slattery/swagger-ui-viewer
                ^^^^       ^^^^^^^^^^^^^^^^^^^^^^^^^
```

For fun, here's a one-liner to pull and run the image, and launch a browser with the results:
```bash
$ docker pull slattery/swagger-ui-viewer && docker run --rm -p 8080:80 -v $PWD/swagger/swagger.json:/www/swagger.json slattery/swagger-ui-viewer | (sleep 1 && open http://localhost:8080)
```
