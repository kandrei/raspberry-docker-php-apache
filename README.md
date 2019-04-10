# Dockerfile for PHP-APACHE on Raspberry

[https://hub.docker.com/r/webdevops/php-apache](webdevops/php-apache) is a great image for hosting PHP applications in docker
containers. It has PHP 7.0 as FPM, Apache and also cron, which makes it good for hosting small to medium web applications. The
only problem is that it's not working on ARM, so I had put together a Dockerfile to build a similar image based on Raspbian
Stretch. The recipe is built using the debian-9 dockerfiles from webdevops, with some changes to support ARM.

The image structure should be the same as the webdevops one, and it should support the same environment variables. The 
documentation can be found here: [https://dockerfile.readthedocs.io/en/latest/content/DockerImages/dockerfiles/php-apache.html].

The conf/ folder contains configuration files from the [https://github.com/webdevops/Dockerfile] repository with some changes:

- 30-setup-ioncube.sh - Modified to download dynamic ioncube version based on arch (it was hardcoded to x86_64)

Special thanks to Webdevops team!
