# Makefile standards

## Summary

A set of standards for Makefiles across all projects, to supersede RFC012.

## Problem

When setting up/jumping onto a new project - sometimes it can be hard to discover what commands need to be run to perform common tasks (e.g. Running tests, serving the local development environment). This can make switching between projects more difficult as there can be a large number of ways to perform all of these tasks.

Having a standard set of commands that can be run across all projects for common tasks allows people to get projects up and running without having to spend time looking into how things are set up to know what specific commands to run.

## Proposal

All projects **MUST** have a Makefile.

All projects **MUST** have any relevant targets defined as [`PHONY` targets](https://www.gnu.org/software/make/manual/html_node/Phony-Targets.html) specified on just the first line of the file.

All targets specified in this RFC **MUST** appear above any additional targets in the `Makefile`.

**All** projects **MUST** have the commands:
- `make test`
  - Runs the tests for the project
  - This **MAY** run the tests in a 'watch' mode (e.g. [Guard](https://github.com/guard/guard))
  - This **MAY** have optional arguments for running a specific test/file
- `make setup`
  - Runs the setup for the project
  - E.g. Runs `docker-compose build`
- `make lint`
  - Runs all the linting checks for the project
  - E.g. Runs `rubocop`
- `make lint-styling`
  - Runs style related linting checks for the project
  - E.g. Runs `rubocop --only Style,Layout,Lint`
- `make lint-complexity`
  - Runs complexity metrics related linting checks for the project
  - E.g. Runs `rubocop --except Style,Layout,Lint`

If the project is a **web application** it **MUST** have the commands:
- `make serve`
  - Runs the development version of the application, e.g. Running `docker-compose up`

If the project needs compiling for deployment it **MUST** have the commands:
- `make build`
  - Builds the project for production

If the project runs in **Docker** - it **MUST** have the commands:
- `make docker-build`
  - Builds the Docker image for the project
- `make docker-stop`
  - Stops the running Docker containers for the project (e.g. `docker-compose stop`)
- `make docker-down`
  - Removes the running Docker containers for the project (e.g. `docker-compose down`)
- `make shell`
  - Starts a shell session on the Docker image for the project (e.g. `ash`/`bash`)

### Example Makefile

```make
.PHONY: setup shell test serve lint lint-styling lint-complexity docker-stop docker-down docker-build

setup: docker-build

test: setup
	docker-compose run --rm web ./bin/run_tests.sh

serve: setup
	docker-compose run --rm --service-ports web npm start

shell: setup
	docker-compose run --rm web ash

lint:
  docker-compose run --rm web bundle exec rubocop --parallel

lint-styling:
  docker-compose run --rm web bundle exec rubocop --only Style,Layout,Lint --parallel

lint-complexity:
  docker-compose run --rm web bundle exec rubocop --except Style,Layout,Lint --parallel

docker-build:
	docker-compose build

docker-stop:
	docker-compose stop

docker-down:
	docker-compose down
```
