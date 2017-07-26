[ :ref:`aws <cli:aws>` . :ref:`configure <cli:aws configure>` ]

.. _cli:aws configure set:


***
set
***



===========
Description
===========

Set a configuration value from the config file.

The ``aws configure set`` command can be used to set a single configuration
value in the AWS config file.  The ``set`` command supports both the
*qualified* and *unqualified* config values documented in the ``get`` command
(see ``aws configure get help`` for more information).

To set a single value, provide the configuration name followed by the
configuration value.

If the config file does not exist, one will automatically be created.  If the
configuration value already exists in the config file, it will updated with the
new configuration value.

Setting a value for the ``aws_access_key_id``, ``aws_secret_access_key``, or
the ``aws_session_token`` will result in the value being writen to the
shared credentials file (``~/.aws/credentials``).  All other values will
be written to the config file (default location is ``~/.aws/config``).




========
Synopsis
========

::

    aws configure set varname value [--profile profile-name]




=======
Options
=======

``varname`` (string)
The name of the config value to set.

``value`` (string)
The value to set.



========
Examples
========

Given an empty config file, the following commands::

    $ aws configure set aws_access_key_id default_access_key
    $ aws configure set aws_secret_access_key default_secret_key
    $ aws configure set default.region us-west-2
    $ aws configure set default.ca_bundle /path/to/ca-bundle.pem
    $ aws configure set region us-west-1 --profile testing
    $ aws configure set profile.testing2.region eu-west-1
    $ aws configure set preview.cloudsearch true

will produce the following config file::

    [default]
    region = us-west-2
    ca_bundle = /path/to/ca-bundle.pem

    [profile testing]
    region = us-west-1

    [profile testing2]
    region = eu-west-1

    [preview]
    cloudsearch = true

and the following ``~/.aws/credentials`` file::

    [default]
    aws_access_key_id = default_access_key
    aws_secret_access_key = default_secret_key
