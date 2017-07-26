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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/AcceptCertificateTransfer>`_


========
Synopsis
========

::

    accept-certificate-transfer
  --certificate-id <value>
  [--set-as-active | --no-set-as-active]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-id`` (string)


  The ID of the certificate.

  

``--set-as-active`` | ``--no-set-as-active`` (boolean)


  Specifies whether the certificate is active.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None