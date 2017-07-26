[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-network-interfaces:


***************************
describe-network-interfaces
***************************



===========
Description
===========



Describes one or more of your network interfaces.



========
Synopsis
========

::

    describe-network-interfaces
  [--dry-run | --no-dry-run]
  [--network-interface-ids <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--network-interface-ids`` (list)


  One or more network interface IDs.

   

  Default: Describes all your network interfaces.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``addresses.private-ip-address`` - The private IP addresses associated with the network interface. 
   
  * ``addresses.primary`` - Whether the private IP address is the primary IP address associated with the network interface.  
   
  * ``addresses.association.public-ip`` - The association ID returned when the network interface was associated with the Elastic IP address. 
   
  * ``addresses.association.owner-id`` - The owner ID of the addresses associated with the network interface. 
   
  * ``association.association-id`` - The association ID returned when the network interface was associated with an IP address. 
   
  * ``association.allocation-id`` - The allocation ID returned when you allocated the Elastic IP address for your network interface. 
   
  * ``association.ip-owner-id`` - The owner of the Elastic IP address associated with the network interface. 
   
  * ``association.public-ip`` - The address of the Elastic IP address bound to the network interface. 
   
  * ``association.public-dns-name`` - The public DNS name for the network interface. 
   
  * ``attachment.attachment-id`` - The ID of the interface attachment. 
   
  * ``attachment.attach.time`` - The time that the network interface was attached to an instance. 
   
  * ``attachment.delete-on-termination`` - Indicates whether the attachment is deleted when an instance is terminated. 
   
  * ``attachment.device-index`` - The device index to which the network interface is attached. 
   
  * ``attachment.instance-id`` - The ID of the instance to which the network interface is attached. 
   
  * ``attachment.instance-owner-id`` - The owner ID of the instance to which the network interface is attached. 
   
  * ``attachment.nat-gateway-id`` - The ID of the NAT gateway to which the network interface is attached. 
   
  * ``attachment.status`` - The status of the attachment (``attaching`` | ``attached`` | ``detaching`` | ``detached`` ). 
   
  * ``availability-zone`` - The Availability Zone of the network interface. 
   
  * ``description`` - The description of the network interface. 
   
  * ``group-id`` - The ID of a security group associated with the network interface. 
   
  * ``group-name`` - The name of a security group associated with the network interface. 
   
  * ``mac-address`` - The MAC address of the network interface. 
   
  * ``network-interface-id`` - The ID of the network interface. 
   
  * ``owner-id`` - The AWS account ID of the network interface owner. 
   
  * ``private-ip-address`` - The private IP address or addresses of the network interface. 
   
  * ``private-dns-name`` - The private DNS name of the network interface. 
   
  * ``requester-id`` - The ID of the entity that launched the instance on your behalf (for example, AWS Management Console, Auto Scaling, and so on). 
   
  * ``requester-managed`` - Indicates whether the network interface is being managed by an AWS service (for example, AWS Management Console, Auto Scaling, and so on). 
   
  * ``source-desk-check`` - Indicates whether the network interface performs source/destination checking. A value of ``true`` means checking is enabled, and ``false`` means checking is disabled. The value must be ``false`` for the network interface to perform network address translation (NAT) in your VPC.  
   
  * ``status`` - The status of the network interface. If the network interface is not attached to an instance, the status is ``available`` ; if a network interface is attached to an instance the status is ``in-use`` . 
   
  * ``subnet-id`` - The ID of the subnet for the network interface. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``vpc-id`` - The ID of the VPC for the network interface. 
   

  



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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe your network interfaces**

This example describes all your network interfaces.

Command::

  aws ec2 describe-network-interfaces

Output::

  {
    "NetworkInterfaces": [
        {
            "Status": "in-use",
            "MacAddress": "02:2f:8f:b0:cf:75",
            "SourceDestCheck": true,
            "VpcId": "vpc-a01106c2",
            "Description": "my network interface",
            "Association": {
                "PublicIp": "203.0.113.12",
                "AssociationId": "eipassoc-0fbb766a",
                "PublicDnsName": "ec2-203-0-113-12.compute-1.amazonaws.com",
                "IpOwnerId": "123456789012"
            },
            "NetworkInterfaceId": "eni-e5aa89a3",
            "PrivateIpAddresses": [
                {
                    "PrivateDnsName": "ip-10-0-1-17.ec2.internal",
                    "Association": {
                        "PublicIp": "203.0.113.12",
                        "AssociationId": "eipassoc-0fbb766a",
                        "PublicDnsName": "ec2-203-0-113-12.compute-1.amazonaws.com",
                        "IpOwnerId": "123456789012"
                    },
                    "Primary": true,
                    "PrivateIpAddress": "10.0.1.17"
                }
            ],
            "RequesterManaged": false,
            "PrivateDnsName": "ip-10-0-1-17.ec2.internal",
            "AvailabilityZone": "us-east-1d",
            "Attachment": {
                "Status": "attached",
                "DeviceIndex": 1,
                "AttachTime": "2013-11-30T23:36:42.000Z",
                "InstanceId": "i-640a3c17",
                "DeleteOnTermination": false,
                "AttachmentId": "eni-attach-66c4350a",
                "InstanceOwnerId": "123456789012"
            },
            "Groups": [
                {
                    "GroupName": "default",
                    "GroupId": "sg-8637d3e3"
                }
            ],
            "SubnetId": "subnet-b61f49f0",
            "OwnerId": "123456789012",
            "TagSet": [],
            "PrivateIpAddress": "10.0.1.17"
        },
        {
            "Status": "in-use",
            "MacAddress": "02:58:f5:ef:4b:06",
            "SourceDestCheck": true,
            "VpcId": "vpc-a01106c2",
            "Description": "Primary network interface",
            "Association": {
                "PublicIp": "198.51.100.0",
                "IpOwnerId": "amazon"
            },
            "NetworkInterfaceId": "eni-f9ba99bf",
            "PrivateIpAddresses": [
                {
                    "Association": {
                        "PublicIp": "198.51.100.0",
                        "IpOwnerId": "amazon"
                    },
                    "Primary": true,
                    "PrivateIpAddress": "10.0.1.149"
                }
            ],
            "RequesterManaged": false,
            "AvailabilityZone": "us-east-1d",
            "Attachment": {
                "Status": "attached",
                "DeviceIndex": 0,
                "AttachTime": "2013-11-30T23:35:33.000Z",
                "InstanceId": "i-640a3c17",
                "DeleteOnTermination": true,
                "AttachmentId": "eni-attach-1b9db777",
                "InstanceOwnerId": "123456789012"
            },
            "Groups": [
                {
                    "GroupName": "default",
                    "GroupId": "sg-8637d3e3"
                }
            ],
            "SubnetId": "subnet-b61f49f0",
            "OwnerId": "123456789012",
            "TagSet": [],
            "PrivateIpAddress": "10.0.1.149"
        }
    ]
  }


======
Output
======

NetworkInterfaces -> (list)

  

  Information about one or more network interfaces.

  

  (structure)

    

    Describes a network interface.

    

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

      

      

    

  

