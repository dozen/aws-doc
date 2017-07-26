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

 

No notification is sent to the transfer destination's account, it is up to the caller to notify the transfer target.

 

The certificate being transferred must not be in the ACTIVE state. It can be deactivated using the update-certificate API.

 

The certificate must not have any policies attached to it. These can be detached using the detach-principal-policy API.



========
Synopsis
========

::

    transfer-certificate
  --certificate-id <value>
  --target-aws-account <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--certificate-id`` (string)


  The ID of the certificate.

  

``--target-aws-account`` (string)


  The AWS account.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

transferredCertificateArn -> (string)

  

  The ARN of the certificate.

  

  

