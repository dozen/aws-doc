[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot attach-principal-policy:


***********************
attach-principal-policy
***********************



===========
Description
===========



Attaches the specified policy to the specified principal (certificate or other credential).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/AttachPrincipalPolicy>`_


========
Synopsis
========

::

    attach-principal-policy
  --policy-name <value>
  --principal <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--policy-name`` (string)


  The policy name.

  

``--principal`` (string)


  The principal, which can be a certificate ARN (as returned from the CreateCertificate operation) or an Amazon Cognito ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None