[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail get-key-pair:


************
get-key-pair
************



===========
Description
===========



Returns information about a specific key pair.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/GetKeyPair>`_


========
Synopsis
========

::

    get-key-pair
  --key-pair-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--key-pair-name`` (string)


  The name of the key pair for which you are requesting information.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

keyPair -> (structure)

  

  An array of key-value pairs containing information about the key pair.

  

  name -> (string)

    

    The friendly name of the SSH key pair.

    

    

  arn -> (string)

    

    The Amazon Resource Name (ARN) of the key pair (e.g., ``arn:aws:lightsail:us-east-1:123456789101:KeyPair/05859e3d-331d-48ba-9034-12345EXAMPLE`` ).

    

    

  supportCode -> (string)

    

    The support code. Include this code in your email to support when you have questions about an instance or another resource in Lightsail. This code enables our support team to look up your Lightsail information more easily.

    

    

  createdAt -> (timestamp)

    

    The timestamp when the key pair was created (e.g., ``1479816991.349`` ).

    

    

  location -> (structure)

    

    The region name and Availability Zone where the key pair was created.

    

    availabilityZone -> (string)

      

      The Availability Zone. Follows the format ``us-east-1a`` (case-sensitive).

      

      

    regionName -> (string)

      

      The AWS Region name.

      

      

    

  resourceType -> (string)

    

    The resource type (usually ``KeyPair`` ).

    

    

  fingerprint -> (string)

    

    The RSA fingerprint of the key pair.

    

    

  

