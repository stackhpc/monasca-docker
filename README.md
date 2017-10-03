Dockerfiles for Monasca
=======================

[![Build Status](https://travis-ci.org/monasca/monasca-docker.svg?branch=master)](https://travis-ci.org/monasca/monasca-docker)

This repository contains resources for building and deploying a full Monasca
stack in Docker and Kubernetes environments.

Requirements
------------

 * docker, version >= 1.13 recommended
 * docker-compose >= 1.9.0
 * at least 4 GiB of RAM
 * 2 CPUs (cores) or more recommended

Quick Start
-----------

To quickly get a Monasca environment running, you can use [docker-compose][1]:

    docker-compose up

Assuming all goes well, the following services should be exposed on your host
machine:

 * keystone on ports 5000 and 35357
   * see [`preload.yml`][2] for full account info
 * monasca-api on port 8070
 * grafana on port 3000
   * log in with `mini-mon` and `password` (or any valid keystone account)

If needed, `docker-compose rm` can be used to completely clean the environment
between runs.





[1]: https://docs.docker.com/compose/
[2]: https://github.com/hpcloud-mon/monasca-docker/blob/master/keystone/preload.yml
[3]: https://docs.docker.com/compose/environment-variables/
