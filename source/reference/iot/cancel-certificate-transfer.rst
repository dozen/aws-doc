[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot cancel-certificate-transfer:


***************************
cancel-certificate-transfer
***************************



===========
Description
===========



Cancels a pending transfer for the specified certificate.

 

**Note** Only the transfer source account can use this operation to cancel a transfer (transfer destinations can use  reject-certificate-transfer instead). After transfer, AWS IoT returns the certificate to the source account in the INACTIVE state. Once the destination account has accepted the transfer, the transfer may no longer be cancelled.

 

After a certificate transfer is cancelled, the status of the certificate changes from PENDING_TRANSFER to INACTIVE.



========
Synopsis
========

::

    cancel-certificate-transfer
  --certificate-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--certificate-id`` (string)


  The ID of the certificate.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None