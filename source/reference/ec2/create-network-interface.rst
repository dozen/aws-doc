[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-network-interface:


************************
create-network-interface
************************



===========
Description
===========



Creates a network interface in the specified subnet.

 

For more information about network interfaces, see `Elastic Network Interfaces <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html>`_ in the *Amazon Virtual Private Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateNetworkInterface>`_


========
Synopsis
========

::

    create-network-interface
  [--description <value>]
  [--dry-run | --no-dry-run]
  [--groups <value>]
  [--ipv6-address-count <value>]
  [--ipv6-addresses <value>]
  [--private-ip-address <value>]
  [--private-ip-addresses <value>]
  [--secondary-private-ip-address-count <value>]
  --subnet-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--description`` (string)


  A description for the network interface.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--groups`` (list)


  The IDs of one or more security groups.

  



Syntax::

  "string" "string" ...



``--ipv6-address-count`` (integer)


  The number of IPv6 addresses to assign to a network interface. Amazon EC2 automatically selects the IPv6 addresses from the subnet range. You can't use this option if specifying specific IPv6 addresses. If your subnet has the ``AssignIpv6AddressOnCreation`` attribute set to ``true`` , you can specify ``0`` to override this setting.

  

``--ipv6-addresses`` (list)


  One or more specific IPv6 addresses from the IPv6 CIDR block range of your subnet. You can't use this option if you're specifying a number of IPv6 addresses.

  



Shorthand Syntax::

    Ipv6Address=string ...




JSON Syntax::

  [
    {
      "Ipv6Address": "string"
    }
    ...
  ]



``--private-ip-address`` (string)


  The primary private IPv4 address of the network interface. If you don't specify an IPv4 address, Amazon EC2 selects one for you from the subnet's IPv4 CIDR range. If you specify an IP address, you cannot indicate any IP addresses specified in ``privateIpAddresses`` as primary (only one IP address can be designated as primary).

  

``--private-ip-addresses`` (list)


  One or more private IPv4 addresses.

  



Shorthand Syntax::

    Primary=boolean,PrivateIpAddress=string ...




JSON Syntax::

  [
    {
      "Primary": true|false,
      "PrivateIpAddress": "string"
    }
    ...
  ]



``--secondary-private-ip-address-count`` (integer)


  The number of secondary private IPv4 addresses to assign to a network interface. When you specify a number of secondary IPv4 addresses, Amazon EC2 selects these IP addresses within the subnet's IPv4 CIDR range. You can't specify this option and specify more than one private IP address using ``privateIpAddresses`` .

   

  The number of IP addresses you can assign to a network interface varies by instance type. For more information, see `IP Addresses Per ENI Per Instance Type <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html#AvailableIpPerENI>`_ in the *Amazon Virtual Private Cloud User Guide* .

  

``--subnet-id`` (string)


  The ID of the subnet to associate with the network interface.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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
          "Ipv6Addresses": [], 
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

  

  Association -> (structure)

    

    The association information for an Elastic IP address (IPv4) associated with the network interface.

    

    AllocationId -> (string)

      

      The allocation ID.

      

      

    AssociationId -> (string)

      

      The association ID.

      

      

    IpOwnerId -> (string)

      

      The ID of the Elastic IP address owner.

      

      

    PublicDnsName -> (string)

      

      The public DNS name.

      

      

    PublicIp -> (string)

      

      The address of the Elastic IP address bound to the network interface.

      

      

    

  Attachment -> (structure)

    

    The network interface attachment.

    

    AttachTime -> (timestamp)

      

      The timestamp indicating when the attachment initiated.

      

      

    AttachmentId -> (string)

      

      The ID of the network interface attachment.

      

      

    DeleteOnTermination -> (boolean)

      

      Indicates whether the network interface is deleted when the instance is terminated.

      

      

    DeviceIndex -> (integer)

      

      The device index of the network interface attachment on the instance.

      

      

    InstanceId -> (string)

      

      The ID of the instance.

      

      

    InstanceOwnerId -> (string)

      

      The AWS account ID of the owner of the instance.

      

      

    Status -> (string)

      

      The attachment state.

      

      

    

  AvailabilityZone -> (string)

    

    The Availability Zone.

    

    

  Description -> (string)

    

    A description.

    

    

  Groups -> (list)

    

    Any security groups for the network interface.

    

    (structure)

      

      Describes a security group.

      

      GroupName -> (string)

        

        The name of the security group.

        

        

      GroupId -> (string)

        

        The ID of the security group.

        

        

      

    

  InterfaceType -> (string)

    

    The type of interface.

    

    

  Ipv6Addresses -> (list)

    

    The IPv6 addresses associated with the network interface.

    

    (structure)

      

      Describes an IPv6 address associated with a network interface.

      

      Ipv6Address -> (string)

        

        The IPv6 address.

        

        

      

    

  MacAddress -> (string)

    

    The MAC address.

    

    

  NetworkInterfaceId -> (string)

    

    The ID of the network interface.

    

    

  OwnerId -> (string)

    

    The AWS account ID of the owner of the network interface.

    

    

  PrivateDnsName -> (string)

    

    The private DNS name.

    

    

  PrivateIpAddress -> (string)

    

    The IPv4 address of the network interface within the subnet.

    

    

  PrivateIpAddresses -> (list)

    

    The private IPv4 addresses associated with the network interface.

    

    (structure)

      

      Describes the private IPv4 address of a network interface.

      

      Association -> (structure)

        

        The association information for an Elastic IP address (IPv4) associated with the network interface.

        

        AllocationId -> (string)

          

          The allocation ID.

          

          

        AssociationId -> (string)

          

          The association ID.

          

          

        IpOwnerId -> (string)

          

          The ID of the Elastic IP address owner.

          

          

        PublicDnsName -> (string)

          

          The public DNS name.

          

          

        PublicIp -> (string)

          

          The address of the Elastic IP address bound to the network interface.

          

          

        

      Primary -> (boolean)

        

        Indicates whether this IPv4 address is the primary private IPv4 address of the network interface.

        

        

      PrivateDnsName -> (string)

        

        The private DNS name.

        

        

      PrivateIpAddress -> (string)

        

        The private IPv4 address.

        

        

      

    

  RequesterId -> (string)

    

    The ID of the entity that launched the instance on your behalf (for example, AWS Management Console or Auto Scaling).

    

    

  RequesterManaged -> (boolean)

    

    Indicates whether the network interface is being managed by AWS.

    

    

  SourceDestCheck -> (boolean)

    

    Indicates whether traffic to or from the instance is validated.

    

    

  Status -> (string)

    

    The status of the network interface.

    

    

  SubnetId -> (string)

    

    The ID of the subnet.

    

    

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

        

        

      

    

  VpcId -> (string)

    

    The ID of the VPC.

    

    

  

