[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot transfer-certificate:


********************
transfer-certificate
********************



===========
Description
===========



Transfers the specified certificate to the specified AWS account.

 

You can cancel the transfer until it is acknowledged by the recipient.

 

No notification is sent to the transfer destination's account. It is up to the caller to notify the transfer target.

 

The certificate being transferred must not be in the ACTIVE state. You can use the update-certificate API to deactivate it.

 

The certificate must not have any policies attached to it. You can use the detach-principal-policy API to detach them.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/TransferCertificate>`_


========
Synopsis
========

::

    transfer-certificate
  --certificate-id <value>
  --target-aws-account <value>
  [--transfer-message <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-id`` (string)


  The ID of the certificate.

  

``--target-aws-account`` (string)


  The AWS account.

  

``--transfer-message`` (string)


  The transfer message.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

transferredCertificateArn -> (string)

  

  The ARN of the certificate.

  

  

