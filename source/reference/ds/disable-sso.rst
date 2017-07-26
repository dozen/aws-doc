[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds disable-sso:


***********
disable-sso
***********



===========
Description
===========



Disables single-sign on for a directory.



========
Synopsis
========

::

    disable-sso
  --directory-id <value>
  [--user-name <value>]
  [--password <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--directory-id`` (string)


  The identifier of the directory for which to disable single-sign on.

  

``--user-name`` (string)


  The username of an alternate account to use to disable single-sign on. This is only used for AD Connector directories. This account must have privileges to remove a service principal name. 

   

  If the AD Connector service account does not have privileges to remove a service principal name, you can specify an alternate account with the *user-name* and *Password* parameters. These credentials are only used to disable single sign-on and are not stored by the service. The AD Connector service account is not changed.

  

``--password`` (string)


  The password of an alternate account to use to disable single-sign on. This is only used for AD Connector directories. For more information, see the *user-name* parameter.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

