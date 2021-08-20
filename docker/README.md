# Modular Docker Builds <img src='_assets/logo.png' align="right" height="139" /></a>

The purpose of this repo is to serve as a base Docker build definition that is customizable depending on the needs of a project, tool, or workflow.

This repo is set on Github as a template repo, which means you can clone the repo and have the same base structure, from which you can define your own Docker image specification for your project.

## Organization

* `_assets/` - where the logo for this repo lives; you can safely ignore this
* `custom_scripts/<theme>/<script.sh>` - the heart of the repo that contains working scripts that install desired tools, creating the necessary custom Docker environment for your needs. These are called by the Dockerfile on an ad-hoc basis. Each collection is comprised of bash scripts that perform the necessary installation processes.
* `Dockerfile` - the core docker image build instructions

The `custom_scripts/` folder contains themed collections of scripts that install a variety of software. Which scripts are called is dependent on the Dockerfile build instructions, where one can add/subtract/modify existing calls to these scripts.

## Building your Docker Image

To build the docker image, run the docker build command within this folder (reference the `_build-docker.sh` script for a template). Note that the `-t <image-name>` flag should be changed to describe your Docker's utility). 

## Using this Repo

Clone this repo, modify/add scripts as needed, and then run the Docker build. Your repo should be a separate repo from this one (or embedded into an existing project). 

## Contributing

There are several ways to contribute to this repo. 

For direct changes to the codebase, create a new feature branch and add new scripts, fix existing ones, and whatever else you think of that would help this template repo become more useful. Once finished, submit a PR for review to merge into the main branch.

Problems? Commentary? Discussion? Questions? File an issue up at the top of this GH repo.

## Contact

Reach out to Rob at robert.amezquita@pfizer.com.
