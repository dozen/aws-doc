[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot update-certificate:


******************
update-certificate
******************



===========
Description
===========



Updates the status of the specified certificate. This operation is idempotent.

 

Moving a cert from the ACTIVE state (including REVOKED) will NOT disconnect currently-connected devices, although these devices will be unable to reconnect.

 

The ACTIVE state is required to authenticate devices connecting to AWS IoT using a certificate.



========
Synopsis
========

::

    update-certificate
  --certificate-id <value>
  --new-status <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--certificate-id`` (string)


  The ID of the certificate.

  

``--new-status`` (string)


  The new status.

   

  Note: setting the status to PENDING_TRANSFER will result in an exception being thrown. PENDING_TRANSFER is a status used internally by AWS IoT and is not meant to be used by developers.

  

  Possible values:

  
  *   ``ACTIVE``

  
  *   ``INACTIVE``

  
  *   ``REVOKED``

  
  *   ``PENDING_TRANSFER``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None