[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot reject-certificate-transfer:


***************************
reject-certificate-transfer
***************************



===========
Description
===========



Rejects a pending certificate transfer. After AWS IoT rejects a certificate transfer, the certificate status changes from **PENDING_TRANFER** to **INACTIVE** .

 

To check for pending certificate transfers, call  list-certificates to enumerate your certificates.

 

This operation can only be called by the transfer destination. Once called, the certificate will be returned to the source's account in the INACTIVE state.



========
Synopsis
========

::

    reject-certificate-transfer
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