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

If all are ok, you can enter http://localhost:5000/ in a browser to see 
the application running.


.. image:: https://raw.githubusercontent.com/macagua/example.dockercompose.getstarted/master/docs/_static/screenshot_1.png
   :height: 160px
   :width: 486px
   :alt: The Web container running
   :align: left


If you refresh your browser the Web container return a new message, like this follow:

.. image:: https://raw.githubusercontent.com/macagua/example.dockercompose.getstarted/master/docs/_static/screenshot_2.png
   :height: 159px
   :width: 486px
   :alt: The Web container refreshed
   :align: left

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

You need rebuild your Docker image project when was changed, for that
executing the follow command:

::

  $ docker-compose -p composetest up --build

In this previous command you indicate with the parameter ``-p`` the
name of the project as ``composetest``, also you indicate with the
parameter ``--build`` that to build images before starting containers.


Inspect service running
=======================

For see what environment variables are available to the ``web`` service,
executing the follow command:

::

  $ docker-compose -p composetest run web env
  PATH=/usr/local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
  HOSTNAME=813f4a22d6c5
  TERM=xterm
  FLASK_ENV=development
  LANG=C.UTF-8
  GPG_KEY=0D96DF4D4110E5C43FBFB17F2D347EA6AA65421D
  PYTHON_VERSION=3.7.7
  PYTHON_PIP_VERSION=20.1
  PYTHON_GET_PIP_URL=https://github.com/pypa/get-pip/raw/1fe530e9e3d800be94e04f6428460fc4fb94f5a9/get-pip.py
  PYTHON_GET_PIP_SHA256=ce486cddac44e99496a702aa5c06c5028414ef48fdfd5242cd2fe559b13d4348
  FLASK_APP=app.py
  FLASK_RUN_HOST=0.0.0.0
  HOME=/root


Stopping project
================

For stopping your Docker containers project, executing the follow
command:

::

  $ docker-compose -p composetest stop

In this previous command you indicate with the parameter ``-p`` the
name of the project as ``composetest``.

With the ``stop`` option, let you to stop your running Docker
containers without removing them. They can be started again with
the command ``docker-compose -p composetest start``.


Downing containers
==================

For bring everything down, removing the containers entirely, with the ``down``
command. If you started your Docker Compose with ``docker-compose -p composetest up -d``
command, stop your services once you've finished with them:

::

  $ docker-compose -p composetest down

In this previous command you indicate with the parameter ``-p`` the
name of the project as ``composetest``.

With the ``down`` option, let you to stops containers and removes containers,
networks, volumes, and images created by the ``up`` command option.

Pass the parameter ``--volumes`` to also remove the data volume used by the
container, executing the follow command:

::

  $ docker-compose -p composetest down --volumes


Contribute
==========

- `Source code @ GitHub <https://github.com/macagua/example.dockercompose.getstarted.git>`_.
- `Issues @ GitHub <https://github.com/macagua/example.dockercompose.getstarted/issues>`_.


License
=======

The project is licensed under the MIT.

.. _`Get started with Docker Compose`: https://docs.docker.com/compose/gettingstarted/
.. _`Flask`: http://flask.pocoo.org/
.. _`Redis`: https://redis.io/

