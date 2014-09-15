docker-composer-hhvm
====================

Run composer on hhvm within a docker container

So instead of running

    $ composer install

You can run

    $ docker run --rm=true -ti -v `pwd`:/srv marmelab/composer-hhvm bash -c 'hhvm /usr/local/bin/composer install'

The entrypoint is voluntarily omitted to ease user manipulation in the container in order to have composer generate files with the correct user rights.
