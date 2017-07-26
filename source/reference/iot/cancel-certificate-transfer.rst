[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot cancel-certificate-transfer:


***************************
cancel-certificate-transfer
***************************



===========
Description
===========



Cancels a pending transfer for the specified certificate.

 

 **Note** Only the transfer source account can use this operation to cancel a transfer. (Transfer destinations can use  reject-certificate-transfer instead.) After transfer, AWS IoT returns the certificate to the source account in the INACTIVE state. After the destination account has accepted the transfer, the transfer cannot be cancelled.

 

After a certificate transfer is cancelled, the status of the certificate changes from PENDING_TRANSFER to INACTIVE.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/CancelCertificateTransfer>`_


========
Synopsis
========

::

    cancel-certificate-transfer
  --certificate-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-id`` (string)


  The ID of the certificate.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None