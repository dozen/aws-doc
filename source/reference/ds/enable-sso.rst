[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds enable-sso:


**********
enable-sso
**********



===========
Description
===========



Enables single sign-on for a directory.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/EnableSso>`_


========
Synopsis
========

::

    enable-sso
  --directory-id <value>
  [--user-name <value>]
  [--password <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-id`` (string)


  The identifier of the directory for which to enable single-sign on.

  

``--user-name`` (string)


  The username of an alternate account to use to enable single-sign on. This is only used for AD Connector directories. This account must have privileges to add a service principal name.

   

  If the AD Connector service account does not have privileges to add a service principal name, you can specify an alternate account with the *user-name* and *Password* parameters. These credentials are only used to enable single sign-on and are not stored by the service. The AD Connector service account is not changed.

  

``--password`` (string)


  The password of an alternate account to use to enable single-sign on. This is only used for AD Connector directories. For more information, see the *user-name* parameter.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

