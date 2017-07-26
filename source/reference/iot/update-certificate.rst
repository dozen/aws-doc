[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot update-certificate:


******************
update-certificate
******************



===========
Description
===========



Updates the status of the specified certificate. This operation is idempotent.

 

Moving a certificate from the ACTIVE state (including REVOKED) will not disconnect currently connected devices, but these devices will be unable to reconnect.

 

The ACTIVE state is required to authenticate devices connecting to AWS IoT using a certificate.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/UpdateCertificate>`_


========
Synopsis
========

::

    update-certificate
  --certificate-id <value>
  --new-status <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-id`` (string)


  The ID of the certificate.

  

``--new-status`` (string)


  The new status.

   

   **Note:** Setting the status to PENDING_TRANSFER will result in an exception being thrown. PENDING_TRANSFER is a status used internally by AWS IoT. It is not intended for developer use.

   

   **Note:** The status value REGISTER_INACTIVE is deprecated and should not be used.

  

  Possible values:

  
  *   ``ACTIVE``

  
  *   ``INACTIVE``

  
  *   ``REVOKED``

  
  *   ``PENDING_TRANSFER``

  
  *   ``REGISTER_INACTIVE``

  
  *   ``PENDING_ACTIVATION``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None