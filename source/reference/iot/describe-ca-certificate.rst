[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot describe-ca-certificate:


***********************
describe-ca-certificate
***********************



===========
Description
===========



Describes a registered CA certificate.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/DescribeCACertificate>`_


========
Synopsis
========

::

    describe-ca-certificate
  --certificate-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-id`` (string)


  The CA certificate identifier.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

certificateDescription -> (structure)

  

  The CA certificate description.

  

  certificateArn -> (string)

    

    The CA certificate ARN.

    

    

  certificateId -> (string)

    

    The CA certificate ID.

    

    

  status -> (string)

    

    The status of a CA certificate.

    

    

  certificatePem -> (string)

    

    The CA certificate data, in PEM format.

    

    

  ownedBy -> (string)

    

    The owner of the CA certificate.

    

    

  creationDate -> (timestamp)

    

    The date the CA certificate was created.

    

    

  autoRegistrationStatus -> (string)

    

    Whether the CA certificate configured for auto registration of device certificates. Valid values are "ENABLE" and "DISABLE"

    

    

  

