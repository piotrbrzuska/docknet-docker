# docknet-docker - a docker proxy for dotnet

This is a proxy for Microsoft dotnet for unsupported platforms.

Proxy based on docker platform: it use docker image (https://hub.docker.com/r/microsoft/dotnet/) released by Microsoft.

Tested on:
* Arch linux 

let me know if your system is running or not!


**based on** https://github.com/RendleLabs/docknet-docker

Original readme.md:

# docknet-docker
A Docker image for using the dotnet CLI and CoreRT on any(?) Linux


## TL;DR

1. Copy the `docknet` script to somewhere on your path (and make sure it's executable).
2. Create a directory (on the host) for your app and `cd` into it.
3. Use `docknet` instead of `dotnet`.
## Why is this?

Right now, [CoreRT](https://github.com/dotnet/corert) and [the .NET CLI](https://github.com/dotnet/cli) only work on a limited range of Linux distros.
I tried running an Ubuntu 14.04 as my main OS for a week and it was awful, so I went back to Manjaro, but I still want to play with .NET Core.
This combination of a Docker image based on `ubuntu:trusty` with `dotnet-nightly` installed, and a little shell script that runs the container
mounting the relevant directories from your host machine into it so all the files produced are on your machine, and not in the Docker container.

## Is it finished?

It works, but I'm sure it could use some enhancements, so feel free to send me PRs if you see anything that could be improved.

## How often is it updated?

There's a [Zapier](https://zapier.com) scheduled webhook set up to build a new image every day at 3am, and it will pick up the latest
`dotnet-nightly` every time that runs, so you might want to `docker pull rendlelabs/docknet` regularly.
