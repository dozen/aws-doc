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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudhsm-2014-05-30/ModifyLunaClient>`_


========
Synopsis
========

::

    modify-luna-client
  --client-arn <value>
  --certificate <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--client-arn`` (string)


  The ARN of the client.

  

``--certificate`` (string)


  The new certificate for the client.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ClientArn -> (string)

  

  The ARN of the client.

  

  

