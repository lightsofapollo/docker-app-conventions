# Docker App Conventions (for projects built with docker)

## Layout

At minimum there are two different aspects to a particular repo. Things that can happen external to the docker container (like running docker build) and things that run inside the docker container.

Everything not explictly mentioned as external are internal to the docker container (but read the Dockerfile).

External files (this may or may not be in every repo but they follow the convention if present):

  - Dockerfile: Obviously we need some way to build the docker image
  - Makefile: should be used to _build_ and test the project from an external perspective

## Testing

"Testing" in a true sense should always be done _on_ the docker image. It can be tested purely via an external inteface (like making http requests) or internally by invoking the (language specific tests) for the docker image.
