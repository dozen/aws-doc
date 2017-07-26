[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm get-config:


**********
get-config
**********



===========
Description
===========



Gets the configuration files necessary to connect to all high availability partition groups the client is associated with.



========
Synopsis
========

::

    get-config
  --client-arn <value>
  --client-version <value>
  --hapg-list <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--client-arn`` (string)


  The ARN of the client.

  

``--client-version`` (string)


  The client version.

  

  Possible values:

  
  *   ``5.1``

  
  *   ``5.3``

  

  

``--hapg-list`` (list)


  A list of ARNs that identify the high-availability partition groups that are associated with the client.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ConfigType -> (string)

  

  The type of credentials.

  

  

ConfigFile -> (string)

  

  The chrystoki.conf configuration file.

  

  

ConfigCred -> (string)

  

  The certificate file containing the server.pem files of the HSMs.

  

  

