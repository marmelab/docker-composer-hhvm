docker-composer-hhvm
====================

Run composer on hhvm within a docker container

So instead of running

    $ composer install

You can run

    $ docker run -ti -v `pwd`:/srv marmelab/composer-hhvm hhvm /usr/local/bin/composer install
    $ #or more simply
    $ docker run -ti -v `pwd`:/srv marmelab/composer-hhvm install

To generate files with the correct user rights inject the userId and groupId in container's environment variable

    $ docker run -ti -e DOCKER_UID=`id -u` -e DOCKER_GID=`id -g` -v `pwd`:/srv marmelab/composer-hhvm install

For using your ssh key, mount your ssh folder and indicate the mount point throught environnement variable

    $ docker run -ti -e DOCKER_SSH=/tmp/ssh -v `pwd`:/srv -v ~/.ssh:/tmp/ssh marmelab/composer-hhvm install
