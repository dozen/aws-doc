[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot describe-certificate:


********************
describe-certificate
********************



===========
Description
===========



Gets information about the specified certificate.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/DescribeCertificate>`_


========
Synopsis
========

::

    describe-certificate
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

certificateDescription -> (structure)

  

  The description of the certificate.

  

  certificateArn -> (string)

    

    The ARN of the certificate.

    

    

  certificateId -> (string)

    

    The ID of the certificate.

    

    

  caCertificateId -> (string)

    

    The certificate ID of the CA certificate used to sign this certificate.

    

    

  status -> (string)

    

    The status of the certificate.

    

    

  certificatePem -> (string)

    

    The certificate data, in PEM format.

    

    

  ownedBy -> (string)

    

    The ID of the AWS account that owns the certificate.

    

    

  previousOwnedBy -> (string)

    

    The ID of the AWS account of the previous owner of the certificate.

    

    

  creationDate -> (timestamp)

    

    The date and time the certificate was created.

    

    

  lastModifiedDate -> (timestamp)

    

    The date and time the certificate was last modified.

    

    

  transferData -> (structure)

    

    The transfer data.

    

    transferMessage -> (string)

      

      The transfer message.

      

      

    rejectReason -> (string)

      

      The reason why the transfer was rejected.

      

      

    transferDate -> (timestamp)

      

      The date the transfer took place.

      

      

    acceptDate -> (timestamp)

      

      The date the transfer was accepted.

      

      

    rejectDate -> (timestamp)

      

      The date the transfer was rejected.

      

      

    

  

