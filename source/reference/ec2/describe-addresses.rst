[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-addresses:


******************
describe-addresses
******************



===========
Description
===========



Describes one or more of your Elastic IP addresses.

 

An Elastic IP address is for use in either the EC2-Classic platform or in a VPC. For more information, see `Elastic IP Addresses <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeAddresses>`_


========
Synopsis
========

::

    describe-addresses
  [--filters <value>]
  [--public-ips <value>]
  [--allocation-ids <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

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



``--public-ips`` (list)


  [EC2-Classic] One or more Elastic IP addresses.

   

  Default: Describes all your Elastic IP addresses.

  



Syntax::

  "string" "string" ...



``--allocation-ids`` (list)


  [EC2-VPC] One or more allocation IDs.

   

  Default: Describes all your Elastic IP addresses.

  



Syntax::

  "string" "string" ...



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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
              "InstanceId": "i-1234567890abcdef0",
              "PublicIp": "198.51.100.0",
              "Domain": "standard"
          },
          {
              "Domain": "vpc",
              "InstanceId": "i-1234567890abcdef0",
              "NetworkInterfaceId": "eni-12345678",
              "AssociationId": "eipassoc-12345678",
              "NetworkInterfaceOwnerId": "123456789012",
              "PublicIp": "203.0.113.0",
              "AllocationId": "eipalloc-12345678",
              "PrivateIpAddress": "10.0.1.241"
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
              "Domain": "vpc",
              "InstanceId": "i-1234567890abcdef0",
              "NetworkInterfaceId": "eni-12345678",
              "AssociationId": "eipassoc-12345678",
              "NetworkInterfaceOwnerId": "123456789012",
              "PublicIp": "203.0.113.0",
              "AllocationId": "eipalloc-12345678",
              "PrivateIpAddress": "10.0.1.241"
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
                "InstanceId": "i-1234567890abcdef0",
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
                "InstanceId": "i-1234567890abcdef0", 
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
                "InstanceId": "i-1234567890abcdef0", 
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

      

      

    

  

