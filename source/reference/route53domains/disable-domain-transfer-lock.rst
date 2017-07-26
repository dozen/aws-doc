[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains disable-domain-transfer-lock:


****************************
disable-domain-transfer-lock
****************************



===========
Description
===========



This operation removes the transfer lock on the domain (specifically the ``clientTransferProhibited`` status) to allow domain transfers. We recommend you refrain from performing this action unless you intend to transfer the domain to a different registrar. Successful submission returns an operation ID that you can use to track the progress and completion of the action. If the request is not completed successfully, the domain registrant will be notified by email.



========
Synopsis
========

::

    disable-domain-transfer-lock
  --domain-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  The name of a domain.

   

  Type: String

   

  Default: None

   

  Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Internationalized Domain Names are not supported.

   

  Required: Yes

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

OperationId -> (string)

  

  Identifier for tracking the progress of the request. To use this ID to query the operation status, use GetOperationDetail.

   

  Type: String

   

  Default: None

   

  Constraints: Maximum 255 characters.

  

  

