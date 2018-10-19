[![Docker Automated buil](https://img.shields.io/docker/automated/moul/smashing.svg?maxAge=2592000)]()
[![](https://images.microbadger.com/badges/image/moul/smashing.svg)](http://microbadger.com/images/moul/smashing)
[![Docker Stars](https://img.shields.io/docker/stars/moul/smashing.svg?maxAge=2592000)]()
[![Docker Pulls](https://img.shields.io/docker/pulls/moul/smashing.svg?maxAge=2592000)]() [![GuardRails badge](https://badges.production.guardrails.io/moul/docker-smashing.svg)](https://www.guardrails.io)

# docker-smashing

Ship your [smashing](http://smashing.io/) as docker image!

The dockerfile uses the official [ruby:alpine](https://hub.docker.com/_/ruby/) base image to be extremly small.
The smashing process will be executed as smashing user, not as root.

Find this image on [hub.docker.com](https://hub.docker.com/r/moul/smashing/).

Based on https://github.com/detached/docker-dashing

# Usage

Use this image as base for your smashing image.

Create a Dockerfile in the root directory of your smashing project containing one simple line:

    FROM moul/smashing

Thats it!

Two `ON BUILD` hooks will add all your files to the image and execute `bundle` on your Gemfile.

# Build

Run `docker build -t mysmashing .` in your project folder.

# Run

To start your application run

    docker run -p 80:8080 mysmashing

To change the port smashing binds to, start the container with additional arguments:

    docker run -p 80:6666 mysmashing start -p 6666
