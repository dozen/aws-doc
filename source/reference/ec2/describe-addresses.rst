[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-addresses:


******************
describe-addresses
******************



===========
Description
===========



Describes one or more of your Elastic IP addresses.

 

An Elastic IP address is for use in either the EC2-Classic platform or in a VPC. For more information, see `Elastic IP Addresses`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    describe-addresses
  [--dry-run | --no-dry-run]
  [--public-ips <value>]
  [--filters <value>]
  [--allocation-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--public-ips`` (list)


  [EC2-Classic] One or more Elastic IP addresses.

   

  Default: Describes all your Elastic IP addresses.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters. Filter names and values are case-sensitive.

   

   
  * ``allocation-id`` - [EC2-VPC] The allocation ID for the address. 
   
  * ``association-id`` - [EC2-VPC] The association ID for the address. 
   
  * ``domain`` - Indicates whether the address is for use in EC2-Classic (``standard`` ) or in a VPC (``vpc`` ). 
   
  * ``instance-id`` - The ID of the instance the address is associated with, if any. 
   
  * ``network-interface-id`` - [EC2-VPC] The ID of the network interface that the address is associated with, if any. 
   
  * ``network-interface-owner-id`` - The AWS account ID of the owner. 
   
  * ``private-ip-address`` - [EC2-VPC] The private IP address associated with the Elastic IP address. 
   
  * ``public-ip`` - The Elastic IP address. 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--allocation-ids`` (list)


  [EC2-VPC] One or more allocation IDs.

   

  Default: Describes all your Elastic IP addresses.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe your Elastic IP addresses**

This example describes your Elastic IP addresses.

Command::

  aws ec2 describe-addresses

Output::

  {
      "Addresses": [
          {
              "InstanceId": null,
              "PublicIp": "198.51.100.0",
              "Domain": "standard"
          },
          {
              "PublicIp": "203.0.113.0",
              "Domain": "vpc",
              "AllocationId": "eipalloc-64d5890a"
          }
      ]
  }

**To describe your Elastic IP addresses for EC2-VPC**

This example describes your Elastic IP addresses for use with instances in a VPC.

Command::

  aws ec2 describe-addresses --filters "Name=domain,Values=vpc"

Output::

  {
      "Addresses": [
          {
              "PublicIp": "203.0.113.0",
              "Domain": "vpc",
              "AllocationId": "eipalloc-64d5890a"
          }
      ]
  }

This example describes the Elastic IP address with the allocation ID ``eipalloc-282d9641``, which is associated with an instance in EC2-VPC.

Command::

    aws ec2 describe-addresses --allocation-ids eipalloc-282d9641

Output::

    {
        "Addresses": [
            {
                "Domain": "vpc",
                "InstanceId": "i-10a64379",
                "NetworkInterfaceId": "eni-1a2b3c4d",
                "AssociationId": "eipassoc-123abc12",
                "NetworkInterfaceOwnerId": "1234567891012",
                "PublicIp": "203.0.113.25",
                "AllocationId": "eipalloc-282d9641",
                "PrivateIpAddress": "10.251.50.12"
            }
        ]
    }

This example describes the Elastic IP address associated with a particular private IP address in EC2-VPC.

Command::

    aws ec2 describe-addresses --filters "Name=private-ip-address,Values=10.251.50.12"

**To describe your Elastic IP addresses in EC2-Classic**

This example describes your Elastic IP addresses for use in EC2-Classic.

Command::

    aws ec2 describe-addresses --filters "Name=domain,Values=standard"
    
Output::

    {
        "Addresses": [
            {
                "InstanceId": null, 
                "PublicIp": "203.0.110.25", 
                "Domain": "standard"
            }
        ]
    }

This example describes the Elastic IP address with the value ``203.0.110.25``, which is associated with an instance in EC2-Classic.

Command::

    aws ec2 describe-addresses --public-ips 203.0.110.25

Output::

    {
        "Addresses": [
            {
                "InstanceId": "i-1a2b3c4d", 
                "PublicIp": "203.0.110.25", 
                "Domain": "standard"
            }
        ]
    }



======
Output
======

Addresses -> (list)

  

  Information about one or more Elastic IP addresses.

  

  (structure)

    

    Describes an Elastic IP address.

    

    InstanceId -> (string)

      

      The ID of the instance that the address is associated with (if any).

      

      

    PublicIp -> (string)

      

      The Elastic IP address.

      

      

    AllocationId -> (string)

      

      The ID representing the allocation of the address for use with EC2-VPC.

      

      

    AssociationId -> (string)

      

      The ID representing the association of the address with an instance in a VPC.

      

      

    Domain -> (string)

      

      Indicates whether this Elastic IP address is for use with instances in EC2-Classic (``standard`` ) or instances in a VPC (``vpc`` ).

      

      

    NetworkInterfaceId -> (string)

      

      The ID of the network interface.

      

      

    NetworkInterfaceOwnerId -> (string)

      

      The ID of the AWS account that owns the network interface.

      

      

    PrivateIpAddress -> (string)

      

      The private IP address associated with the Elastic IP address.

      

      

    

  



.. _Elastic IP Addresses: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html
