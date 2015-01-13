dockerpile
==========

A collection of useful docker Dockerfiles to build docker images. Use these images to play around with, or as a starting point for your next project. 

A guide for installing docker can be found here (https://docs.docker.com/installation). After docker is installed, you can build docker images and can run them in docker containers. 

to build an image in dockerpile...

	docker build -t <imagename/tag> - < <filename>.dock

for example, to build gnuradio image...

	docker build -t gnuradio - < gnuradio.dock

Once the gnuradio images is finished building...

	docker run -it gnuradio bash

drops you into a root shell of an ubuntu 14.04.1 root file system that contains a gnuradio installation. You can do things inside of this "container", however changes will not be persistent until the container is "committed" back to the image. To keep changes, overwrite or create a new image using...

	docker commit <image id> <imagename/tag>

A new image with a new tag can be created, or you can overwrite an existing image. 

A useful way of using a docker container is to run in daemon mode with ssh access. Using the previous gnuradio example...

	docker run -dit gnuradio bash

starts the container in daemon mode, allowiong it to persist and run in the background on the host machine. You can access via ssh if an ssh server daemon is running in the container (there isn't one in the previous example). 

## Description of .dock files:
* gnuradio.dock: Provides a full GNU Radio installation built using the pybombs utility inside of Ubuntu 14.04.1
* grembedded.dock: Provides an environment to cross-compile ARMv7-based GNU Radio applications using the Ubuntu 15.04 alpha. Cross-compilation is provided by the pybombs utility in conjunction with an open-embedded base filesystem, complete with all dependencies for GNU Radio and other Linux applications. More information on embedded gnuradio... http://gnuradio.org/redmine/projects/gnuradio/wiki/Embedded/2 





