# Makefile standards

Superseded by RFC022.

## Summary

A set of standards for Makefiles across all projects

## Problem

When setting up/jumping onto a new project - sometimes it can be hard to discover what commands
need to be run to perform common tasks (e.g. Running tests, serving the local development environment).
This can make switching between projects more difficult as there can be a large number of ways to perform
all of these tasks.

Having a standard set of commands that can be run across all projects for common tasks
allows people to get projects up and running without having to spend time looking into
how things are set up to know what specific commands to run.


## Proposal

All projects **MUST** have a Makefile.

All projects **MUST** have relevant [`PHONY` targets](https://www.gnu.org/software/make/manual/html_node/Phony-Targets.html)

**All** projects **MUST** have the commands:
- `make test`
  - Runs the tests for the project
  - This **MAY** run the tests in a 'watch' mode (e.g. [Guard](https://github.com/guard/guard))
  - This **MAY** have optional arguments for running a specific test/file
- `make setup`
  - Runs the setup for the project
  - E.g. Runs `docker-compose build`

If the project is a **web application** it **MUST** have the commands:
- `make serve`
  - Runs the development version of the application, e.g. Running `docker-compose up`

If the project is an application which needs compiling for deployment it **MUST** have the commands:
- `make build`
  - Builds the application for production

If the project runs in **Docker** - it **MUST** have the commands:
- `make docker-build`
  - Builds the Docker image for the project
- `make docker-down`
  - Stops the running Docker containers for the project (e.g. `docker-compose down`)
- `make shell`
  - Starts a shell session on the Docker image for the project (e.g. `ash`/`bash`)

### Example Makefile

```make
.PHONY: docker-down
docker-down:
	docker-compose down

.PHONY: docker-build
docker-build:
	docker-compose build

.PHONY: shell
shell: docker-down docker-build
	docker-compose run --rm web ash

.PHONY: test
test: docker-down docker-build
	docker-compose run --rm web ./bin/run_tests.sh

.PHONY: serve
serve: docker-down docker-build
	docker-compose run --rm --service-ports web npm start
```
