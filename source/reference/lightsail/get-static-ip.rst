[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail get-static-ip:


*************
get-static-ip
*************



===========
Description
===========



Returns information about a specific static IP.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/GetStaticIp>`_


========
Synopsis
========

::

    get-static-ip
  --static-ip-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--static-ip-name`` (string)


  The name of the static IP in Lightsail.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

staticIp -> (structure)

  

  An array of key-value pairs containing information about the requested static IP.

  

  name -> (string)

    

    The name of the static IP (e.g., ``StaticIP-Virginia-EXAMPLE`` ).

    

    

  arn -> (string)

    

    The Amazon Resource Name (ARN) of the static IP (e.g., ``arn:aws:lightsail:us-east-1:123456789101:StaticIp/9cbb4a9e-f8e3-4dfe-b57e-12345EXAMPLE`` ).

    

    

  supportCode -> (string)

    

    The support code. Include this code in your email to support when you have questions about an instance or another resource in Lightsail. This code enables our support team to look up your Lightsail information more easily.

    

    

  createdAt -> (timestamp)

    

    The timestamp when the static IP was created (e.g., ``1479735304.222`` ).

    

    

  location -> (structure)

    

    The region and Availability Zone where the static IP was created.

    

    availabilityZone -> (string)

      

      The Availability Zone. Follows the format ``us-east-1a`` (case-sensitive).

      

      

    regionName -> (string)

      

      The AWS Region name.

      

      

    

  resourceType -> (string)

    

    The resource type (usually ``StaticIp`` ).

    

    

  ipAddress -> (string)

    

    The static IP address.

    

    

  attachedTo -> (string)

    

    The instance where the static IP is attached (e.g., ``Amazon_Linux-1GB-Virginia-1`` ).

    

    

  isAttached -> (boolean)

    

    A Boolean value indicating whether the static IP is attached.

    

    

  

