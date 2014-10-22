BrightstarDB Docker
===================

This repository contains Docker files and scripts for building images to run BrightstarDB
in a docker container. For more information about Docker, visit https://docker.com/.

** IMPORTANT **

Right now only the develop branch is available, we plan to make the release branch
available in line with our 1.8 release in November/December 2014.

There are two ways to use the files in this repository.

Quick and Easy
--------------

If you want to run a single BrightstarDB database server you can download and run
our docker image from DockerHub with a single command:

docker run -d -t -p=80:8090 -v /brightstardata:/brightstardata brightstardb/brightstardb-develop

Then browse to http://your.host.server/brightstar to start using the browser interface to the store.

**Some notes on the command line**

The -d and -t options just specify the mode that the container runs in, it will be run as a simple,
non-interactive container process.

The -v option maps the /brightstardata folder in the container to a folder on the host (in this
case a folder named /brightstardata) - docker will create this folder on the host if it does
not already exist.

The -p option maps BrightstarDB's default port of 8090 to the container port 80, this means 
that once the container is running you should be able to connect to the BrightstarDB server
from a browser using the address http://your.host.server/brightstar/ (please note the /brightstar/
on the end of the URL!)

Build Yourself
--------------

If you prefer, you can build from the Dockerfile. A simple way to do this would be:

    #. Use git to clone this repository onto your docker host
    #. cd to develop
    #. Build the image using a command like:
        docker build -t "brightstardb/brightstardb-develop"
    #. Run the image, either using the start-bs.sh script provided (if you used our suggested tag),
       or a similar invocation of docker run
       
