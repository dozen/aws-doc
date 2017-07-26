[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds generate-db-auth-token:


**********************
generate-db-auth-token
**********************



===========
Description
===========

Generates an auth token used to connect to a db with IAM credentials.



========
Synopsis
========

::

    generate-db-auth-token
  --hostname <value>
  --port <value>
  --username <value>




=======
Options
=======

``--hostname`` (string)
The hostname of the database to connect to.

``--port`` (integer)
The port number the database is listening on.

``--username`` (string)
The username to log in as.

