Cloud9 v3 Dockerfile
=============

This repository contains Dockerfile of Cloud9 IDE for Docker's automated build published to the public Docker Hub Registry.

# Base Docker Image
[wgbartley/aarch64-supervisor-docker](https://registry.hub.docker.com/u/wgbartley/aarch64-supervisor-docker/)

# Installation

## Install Docker.

Download automated build from public Docker Hub Registry: docker pull wgbartley/aarch64-cloud9-docker

(alternatively, you can build an image from Dockerfile: docker build -t="wgbartley/aarch64-cloud9-docker" github.com/wgbartley/aarch64-cloud9-docker)

## Usage

    docker run -it -d -p 80:80 wgbartley/aarch64-cloud9-docker
    
You can add a workspace as a volume directory with the argument *-v /your-path/workspace/:/workspace/* like this :

    docker run -it -d -p 80:80 -v /your-path/workspace/:/workspace/ wgbartley/aarch64-cloud9-docker
    
## Build and run with custom config directory

Get the latest version from github

    git clone https://github.com/wgbartley/aarch64-cloud9-docker
    cd aarch64-cloud9-docker/

Build it

    sudo docker build --force-rm=true --tag="$USER/aarch64-cloud9-docker:latest" .
    
And run

    sudo docker run -d -p 80:80 -v /your-path/workspace/:/workspace/ $USER/aarch64-cloud9-docker:latest
    
Enjoy !!    


### Credit

This image was built from the original kdelfour/cloud9-docker image with minor tweaks
to work with aarch64/ubuntu (for original intended use on a Pine 64 single board computer).
