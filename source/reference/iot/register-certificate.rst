[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot register-certificate:


********************
register-certificate
********************



===========
Description
===========



Registers a device certificate with AWS IoT. If you have more than one CA certificate that has the same subject field, you must specify the CA certificate that was used to sign the device certificate being registered.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/RegisterCertificate>`_


========
Synopsis
========

::

    register-certificate
  --certificate-pem <value>
  [--ca-certificate-pem <value>]
  [--set-as-active | --no-set-as-active]
  [--status <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-pem`` (string)


  The certificate data, in PEM format.

  

``--ca-certificate-pem`` (string)


  The CA certificate used to sign the device certificate being registered.

  

``--set-as-active`` | ``--no-set-as-active`` (boolean)


  A boolean value that specifies if the CA certificate is set to active.

  

``--status`` (string)


  The status of the register certificate request.

  

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

certificateArn -> (string)

  

  The certificate ARN.

  

  

certificateId -> (string)

  

  The certificate identifier.

  

  

