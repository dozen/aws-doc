[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm modify-luna-client:


******************
modify-luna-client
******************



===========
Description
===========



Modifies the certificate used by the client.

 

This action can potentially start a workflow to install the new certificate on the client's HSMs.



========
Synopsis
========

::

    modify-luna-client
  --client-arn <value>
  --certificate <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--client-arn`` (string)


  The ARN of the client.

  

``--certificate`` (string)


  The new certificate for the client. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ClientArn -> (string)

  

  The ARN of the client.

  

  

