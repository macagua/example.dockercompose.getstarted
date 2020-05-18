================================
example.dockercompose.getstarted
================================

Example from the `Get started with Docker Compose`_ Tutorial.


Features
========

- `Flask`_ web application based.

- `Redis`_ key-value store based.


Starting project
================

For starting your Docker containers project, executing the follow command:

::

  $ docker-compose -p composetest up -d

In this previous command you indicate with the parameter ``-p`` the
name of the project as ``composetest``.

With the ``up`` option, let you to builds, (re)creates, starts, and attaches
to containers for a service. also you indicate with the parameter ``-d``
that the start of the containers is in the background.


Listing images
==============

For listing the Docker images used into your project, executing the follow command:

::

  $ docker-compose -p composetest images
       Container          Repository       Tag       Image Id      Size  
  -----------------------------------------------------------------------
  composetest_redis_1   redis             alpine   b4ceee5c3fa3   30.2 MB
  composetest_web_1     composetest_web   latest   31f31a6391ac   210 MB


Listing containers
==================

For listing the Docker containers created into your project, executing the follow command:

::

  $ docker-compose -p composetest ps
         Name                      Command               State           Ports         
  -------------------------------------------------------------------------------------
  composetest_redis_1   docker-entrypoint.sh redis ...   Up      6379/tcp              
  composetest_web_1     flask run                        Up      0.0.0.0:5000->5000/tcp


Display running processes
=========================

For display the running processes into your Docker project, executing the follow command:

::

  $ docker-compose -p composetest top
  composetest_redis_1
  UID    PID    PPID    C   STIME   TTY     TIME         CMD     
  ---------------------------------------------------------------
  999   12431   12392   0   23:39   ?     00:00:00   redis-server
  
  composetest_web_1
  UID     PID    PPID    C   STIME   TTY     TIME                          CMD                      
  --------------------------------------------------------------------------------------------------
  root   12424   12391   0   23:39   ?     00:00:00   /usr/local/bin/python /usr/local/bin/flask run


Rebuild image project
=====================

For rebuild your Docker image project, executing the follow command:

::

  $ docker-compose -p composetest up --build

In this previous command you indicate with the parameter ``-p`` the
name of the project as ``composetest``, also you indicate with the
parameter ``--build`` that to build images before starting containers.


Stopping project
================

For stopping your Docker containers project, executing the follow command:

::

  $ docker-compose -p composetest down

In this previous command you indicate with the parameter ``-p`` the
name of the project as ``composetest``.

With the ``down`` option, let you to stops containers and removes containers,
networks, volumes, and images created by the `up` command option.

.. _`Get started with Docker Compose`: https://docs.docker.com/compose/gettingstarted/
.. _`Flask`: http://flask.pocoo.org/
.. _`Redis`: https://redis.io/

