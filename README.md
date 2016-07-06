# area51/alpine

This is the base image for the majority of our docker images. It consists of the current alpine:latest image with glibc installed.

It also has curl as an aditional package. This is done as curl is most commonly used in building images and, as the base has wget, it makes sense to keep curl in it.

