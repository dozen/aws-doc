[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-network-interface:


************************
create-network-interface
************************



===========
Description
===========



Creates a network interface in the specified subnet.

 

For more information about network interfaces, see `Elastic Network Interfaces`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    create-network-interface
  --subnet-id <value>
  [--description <value>]
  [--private-ip-address <value>]
  [--groups <value>]
  [--private-ip-addresses <value>]
  [--secondary-private-ip-address-count <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--subnet-id`` (string)


  The ID of the subnet to associate with the network interface.

  

``--description`` (string)


  A description for the network interface.

  

``--private-ip-address`` (string)


  The primary private IP address of the network interface. If you don't specify an IP address, Amazon EC2 selects one for you from the subnet range. If you specify an IP address, you cannot indicate any IP addresses specified in ``privateIpAddresses`` as primary (only one IP address can be designated as primary).

  

``--groups`` (list)


  The IDs of one or more security groups.

  



Syntax::

  "string" "string" ...



``--private-ip-addresses`` (list)


  One or more private IP addresses.

  



Shorthand Syntax::

    PrivateIpAddress=string,Primary=boolean ...




JSON Syntax::

  [
    {
      "PrivateIpAddress": "string",
      "Primary": true|false
    }
    ...
  ]



``--secondary-private-ip-address-count`` (integer)


  The number of secondary private IP addresses to assign to a network interface. When you specify a number of secondary IP addresses, Amazon EC2 selects these IP addresses within the subnet range. You can't specify this option and specify more than one private IP address using ``privateIpAddresses`` .

   

  The number of IP addresses you can assign to a network interface varies by instance type. For more information, see `Private IP Addresses Per ENI Per Instance Type`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a network interface**

This example creates a network interface for the specified subnet.

Command::

  aws ec2 create-network-interface --subnet-id subnet-9d4a7b6c --description "my network interface" --groups sg-903004f8 --private-ip-address 10.0.2.17

Output::

  {
      "NetworkInterface": {
          "Status": "pending",
          "MacAddress": "02:1a:80:41:52:9c",
          "SourceDestCheck": true,
          "VpcId": "vpc-a01106c2",
          "Description": "my network interface",
          "NetworkInterfaceId": "eni-e5aa89a3",
          "PrivateIpAddresses": [
              {
                  "Primary": true,
                  "PrivateIpAddress": "10.0.2.17"
              }
          ],
          "RequesterManaged": false,
          "AvailabilityZone": "us-east-1d",
          "Groups": [
              {
                  "GroupName": "default",
                  "GroupId": "sg-903004f8"
              }
          ],
          "SubnetId": "subnet-9d4a7b6c",
          "OwnerId": "123456789012",
          "TagSet": [],
          "PrivateIpAddress": "10.0.2.17"
      }  
  }

======
Output
======

NetworkInterface -> (structure)

  

  Information about the network interface.

  

  NetworkInterfaceId -> (string)

    

    The ID of the network interface.

    

    

  SubnetId -> (string)

    

    The ID of the subnet.

    

    

  VpcId -> (string)

    

    The ID of the VPC.

    

    

  AvailabilityZone -> (string)

    

    The Availability Zone.

    

    

  Description -> (string)

    

    A description.

    

    

  OwnerId -> (string)

    

    The AWS account ID of the owner of the network interface.

    

    

  RequesterId -> (string)

    

    The ID of the entity that launched the instance on your behalf (for example, AWS Management Console or Auto Scaling).

    

    

  RequesterManaged -> (boolean)

    

    Indicates whether the network interface is being managed by AWS.

    

    

  Status -> (string)

    

    The status of the network interface.

    

    

  MacAddress -> (string)

    

    The MAC address.

    

    

  PrivateIpAddress -> (string)

    

    The IP address of the network interface within the subnet.

    

    

  PrivateDnsName -> (string)

    

    The private DNS name.

    

    

  SourceDestCheck -> (boolean)

    

    Indicates whether traffic to or from the instance is validated.

    

    

  Groups -> (list)

    

    Any security groups for the network interface.

    

    (structure)

      

      Describes a security group.

      

      GroupName -> (string)

        

        The name of the security group.

        

        

      GroupId -> (string)

        

        The ID of the security group.

        

        

      

    

  Attachment -> (structure)

    

    The network interface attachment.

    

    AttachmentId -> (string)

      

      The ID of the network interface attachment.

      

      

    InstanceId -> (string)

      

      The ID of the instance.

      

      

    InstanceOwnerId -> (string)

      

      The AWS account ID of the owner of the instance.

      

      

    DeviceIndex -> (integer)

      

      The device index of the network interface attachment on the instance.

      

      

    Status -> (string)

      

      The attachment state.

      

      

    AttachTime -> (timestamp)

      

      The timestamp indicating when the attachment initiated.

      

      

    DeleteOnTermination -> (boolean)

      

      Indicates whether the network interface is deleted when the instance is terminated.

      

      

    

  Association -> (structure)

    

    The association information for an Elastic IP associated with the network interface.

    

    PublicIp -> (string)

      

      The address of the Elastic IP address bound to the network interface.

      

      

    PublicDnsName -> (string)

      

      The public DNS name.

      

      

    IpOwnerId -> (string)

      

      The ID of the Elastic IP address owner.

      

      

    AllocationId -> (string)

      

      The allocation ID.

      

      

    AssociationId -> (string)

      

      The association ID.

      

      

    

  TagSet -> (list)

    

    Any tags assigned to the network interface.

    

    (structure)

      

      Describes a tag.

      

      Key -> (string)

        

        The key of the tag. 

         

        Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:`` 

        

        

      Value -> (string)

        

        The value of the tag.

         

        Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

        

        

      

    

  PrivateIpAddresses -> (list)

    

    The private IP addresses associated with the network interface.

    

    (structure)

      

      Describes the private IP address of a network interface.

      

      PrivateIpAddress -> (string)

        

        The private IP address.

        

        

      PrivateDnsName -> (string)

        

        The private DNS name.

        

        

      Primary -> (boolean)

        

        Indicates whether this IP address is the primary private IP address of the network interface.

        

        

      Association -> (structure)

        

        The association information for an Elastic IP address associated with the network interface.

        

        PublicIp -> (string)

          

          The address of the Elastic IP address bound to the network interface.

          

          

        PublicDnsName -> (string)

          

          The public DNS name.

          

          

        IpOwnerId -> (string)

          

          The ID of the Elastic IP address owner.

          

          

        AllocationId -> (string)

          

          The allocation ID.

          

          

        AssociationId -> (string)

          

          The association ID.

          

          

        

      

    

  InterfaceType -> (string)

    

    The type of interface. 

    

    

  



.. _Private IP Addresses Per ENI Per Instance Type: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html#AvailableIpPerENI
.. _Elastic Network Interfaces: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html
