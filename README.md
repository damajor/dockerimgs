# dockerimgs
My Docker Images Build files

These images are built automatically, just pull one to try it out :)

## Available images
* `damajor/dockerimgs:openjdk-7-jdk`
* `damajor/dockerimgs:openjdk-7-jre`
* `damajor/dockerimgs:oracle-java7`
* `damajor/dockerimgs:oracle-java8`
* `damajor/dockerimgs:wso2cep-3.1.0`
* `damajor/dockerimgs:wso2mb-2.2.0`

All images are based on `phusion/baseimage` (a Docker tuned Ubuntu, more info @ http://phusion.github.io/baseimage-docker/ or https://github.com/phusion/baseimage-docker).

Java images come with a preconfigured `JAVA_HOME` and java bin in `PATH`.

WSO2 CEP & MB are based on `damajor/dockerimgs:oracle-java8`.

## Run and manage

TODO

# More
Look at the README files in sub directories for additional information.

=======
