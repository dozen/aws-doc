[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail create-key-pair:


***************
create-key-pair
***************



===========
Description
===========



Creates sn SSH key pair.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/CreateKeyPair>`_


========
Synopsis
========

::

    create-key-pair
  --key-pair-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--key-pair-name`` (string)


  The name for your new key pair.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

keyPair -> (structure)

  

  An array of key-value pairs containing information about the new key pair you just created.

  

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

    

    

  

publicKeyBase64 -> (string)

  

  A base64-encoded public key of the ``ssh-rsa`` type.

  

  

privateKeyBase64 -> (string)

  

  A base64-encoded RSA private key.

  

  

operation -> (structure)

  

  An array of key-value pairs containing information about the results of your create key pair request.

  

  id -> (string)

    

    The ID of the operation.

    

    

  resourceName -> (string)

    

    The resource name.

    

    

  resourceType -> (string)

    

    The resource type. 

    

    

  createdAt -> (timestamp)

    

    The timestamp when the operation was initialized (e.g., ``1479816991.349`` ).

    

    

  location -> (structure)

    

    The region and Availability Zone.

    

    availabilityZone -> (string)

      

      The Availability Zone. Follows the format ``us-east-1a`` (case-sensitive).

      

      

    regionName -> (string)

      

      The AWS Region name.

      

      

    

  isTerminal -> (boolean)

    

    A Boolean value indicating whether the operation is terminal.

    

    

  operationDetails -> (string)

    

    Details about the operation (e.g., ``Debian-1GB-Virginia-1`` ).

    

    

  operationType -> (string)

    

    The type of operation. 

    

    

  status -> (string)

    

    The status of the operation. 

    

    

  statusChangedAt -> (timestamp)

    

    The timestamp when the status was changed (e.g., ``1479816991.349`` ).

    

    

  errorCode -> (string)

    

    The error code.

    

    

  errorDetails -> (string)

    

    The error details.

    

    

  

