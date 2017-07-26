[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot register-ca-certificate:


***********************
register-ca-certificate
***********************



===========
Description
===========



Registers a CA certificate with AWS IoT. This CA certificate can then be used to sign device certificates, which can be then registered with AWS IoT. You can register up to 10 CA certificates per AWS account that have the same subject field. This enables you to have up to 10 certificate authorities sign your device certificates. If you have more than one CA certificate registered, make sure you pass the CA certificate when you register your device certificates with the register-certificate API.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/RegisterCACertificate>`_


========
Synopsis
========

::

    register-ca-certificate
  --ca-certificate <value>
  --verification-certificate <value>
  [--set-as-active | --no-set-as-active]
  [--allow-auto-registration | --no-allow-auto-registration]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--ca-certificate`` (string)


  The CA certificate.

  

``--verification-certificate`` (string)


  The private key verification certificate.

  

``--set-as-active`` | ``--no-set-as-active`` (boolean)


  A boolean value that specifies if the CA certificate is set to active.

  

``--allow-auto-registration`` | ``--no-allow-auto-registration`` (boolean)


  Allows this CA certificate to be used for auto registration of device certificates.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

certificateArn -> (string)

  

  The CA certificate ARN.

  

  

certificateId -> (string)

  

  The CA certificate identifier.

  

  

