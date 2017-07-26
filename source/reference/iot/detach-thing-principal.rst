[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot detach-thing-principal:


**********************
detach-thing-principal
**********************



===========
Description
===========



Detaches the specified principal from the specified thing.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/DetachThingPrincipal>`_


========
Synopsis
========

::

    detach-thing-principal
  --thing-name <value>
  --principal <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--thing-name`` (string)


  The name of the thing.

  

``--principal`` (string)


  If the principal is a certificate, this value must be ARN of the certificate. If the principal is an Amazon Cognito identity, this value must be the ID of the Amazon Cognito identity.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

