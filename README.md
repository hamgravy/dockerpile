dockerpile
==========

A collection of useful docker Dockerfiles to build docker images

to build an image in dockerpile...

docker build -t <packagename/tag> - < <filename>.dock

for example, to build gnuradio image...

docker build -t gnuradio/ubuntu14.04.1 - < gnuradio.dock 
