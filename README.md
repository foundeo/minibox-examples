# minibox examples

* Minibox is a tiny docker image that includes CommandBox, Java and an OS (Alpine Linux)
* It is only 78mb (can probably shrink it a bit more too)
* This small size makes it great for quick execution scenarios, eg CI tools, Tasks


## Things built with minibox so far:

* [Fixinator Docker Image](https://hub.docker.com/r/foundeo/fixinator) - minbox + fixinator command installeed
* [CFML CI Tools](https://github.com/foundeo/cfml-ci-tools) - minbox + fixinator, cflint, cfml-compiler, codechecker
* [CFML CI Examples](https://github.com/foundeo/cfml-ci-examples) - uses minibox in serveral ways with Github Actions
* [Fixinator Github Action](https://github.com/foundeo/fixinator-github-action) - a github action built using minibox to scan your CFML code for security issues.


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

## Scheduled Task using CommandBox Task Runners with Minibox

See: <https://github.com/foundeo/minibox-examples/blob/master/.github/workflows/task.yml>