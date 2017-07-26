[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot reject-certificate-transfer:


***************************
reject-certificate-transfer
***************************



===========
Description
===========



Rejects a pending certificate transfer. After AWS IoT rejects a certificate transfer, the certificate status changes from **PENDING_TRANSFER** to **INACTIVE** .

 

To check for pending certificate transfers, call  list-certificates to enumerate your certificates.

 

This operation can only be called by the transfer destination. After it is called, the certificate will be returned to the source's account in the INACTIVE state.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/RejectCertificateTransfer>`_


========
Synopsis
========

::

    reject-certificate-transfer
  --certificate-id <value>
  [--reject-reason <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-id`` (string)


  The ID of the certificate.

  

``--reject-reason`` (string)


  The reason the certificate transfer was rejected.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None