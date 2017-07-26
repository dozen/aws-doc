[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot describe-certificate:


********************
describe-certificate
********************



===========
Description
===========



Gets information about the specified certificate.



========
Synopsis
========

::

    describe-certificate
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

certificateDescription -> (structure)

  

  The description of the certificate.

  

  certificateArn -> (string)

    

    The ARN of the certificate.

    

    

  certificateId -> (string)

    

    The ID of the certificate.

    

    

  status -> (string)

    

    The status of the certificate.

    

    

  certificatePem -> (string)

    

    The certificate data, in PEM format.

    

    

  ownedBy -> (string)

    

    The ID of the AWS account that owns the certificate.

    

    

  creationDate -> (timestamp)

    

    The date and time the certificate was created.

    

    

  lastModifiedDate -> (timestamp)

    

    The date and time the certificate was last modified.

    

    

  

