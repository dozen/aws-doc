[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot accept-certificate-transfer:


***************************
accept-certificate-transfer
***************************



===========
Description
===========



Accepts a pending certificate transfer. The default state of the certificate is INACTIVE.

 

To check for pending certificate transfers, call  list-certificates to enumerate your certificates.



========
Synopsis
========

::

    accept-certificate-transfer
  --certificate-id <value>
  [--set-as-active | --no-set-as-active]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--certificate-id`` (string)


  The ID of the certificate.

  

``--set-as-active`` | ``--no-set-as-active`` (boolean)


  Specifies whether the certificate is active.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None