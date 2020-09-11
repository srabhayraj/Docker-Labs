# Dockerfile Overview

  * A dockerfile is a text file which contains a series of commands or instructions.
  * These instructions are executed in the order in which they are written.
  * Execution of these instructions takes place on a base image.
  * On building the Dockerfile, the successive actions form a new image from the base parent image.

## Some core concepts of Dockerfile
  * Docker container is a runnable instance of an image, which is actually made by writing a readable/writable layer on top of some read-only layers.
  * The parent image used to create another image from a Dockerfile is read-only. When we execute instructions on this parent image, new layers keep adding up. These layers are created when we run docker build command.
  * Each layer is read-only except the last one - this is added to the image for generating a runnable container. This last layer is called “container layer”. All changes made to the container, like making new files, installing applications, etc. are done in this thin layer.
  
  
