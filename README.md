# minibox examples

## Things built with minibox so far:

* [Fixinator Docker Image](https://hub.docker.com/r/foundeo/fixinator) - minbox + fixinator command instaleld
* [CFML CI Tools](https://github.com/foundeo/cfml-ci-tools) - minbox + fixinator, cflint, cfml-compiler, codechecker
* [CFML CI Examples](https://github.com/foundeo/cfml-ci-examples) - uses minibox in serveral ways with Github Actions

## Output Box Version

    docker run -it foundeo/minibox box version

## Box Shell

    docker run -it foundeo/minibox box

## Run Fixinator

     docker run -it -v /web/temp/fixinator-demo/:/code -e FIXINATOR_API_KEY=$FIXINATOR_API_KEY  foundeo/fixinator:latest box fixinator path=/code

This example requires a volume to scan the code

## Task Runner

    docker run -it -v /local/code/:/code foundeo/minibox:latest box task run taskFile=/code/task.cfc

## Task Runner with Dockerfile

See the example `Dockerfile` and `docker-compose.yml` and `task.cfc`

Then run:

    docker-compose up