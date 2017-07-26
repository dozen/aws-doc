[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm create-luna-client:


******************
create-luna-client
******************



===========
Description
===========



Creates an HSM client.



========
Synopsis
========

::

    create-luna-client
  [--label <value>]
  --certificate <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--label`` (string)


  The label for the client.

  

``--certificate`` (string)


  The contents of a Base64-Encoded X.509 v3 certificate to be installed on the HSMs used by this client.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ClientArn -> (string)

  

  The ARN of the client.

  

  

