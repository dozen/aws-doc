[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 run-instances:


*************
run-instances
*************



===========
Description
===========



Launches the specified number of instances using an AMI for which you have permissions. 

 

You can specify a number of options, or leave the default options. The following rules apply:

 

 
* [EC2-VPC] If you don't specify a subnet ID, we choose a default subnet from your default VPC for you. If you don't have a default VPC, you must specify a subnet ID in the request. 
 
* [EC2-Classic] If don't specify an Availability Zone, we choose one for you. 
 
* Some instance types must be launched into a VPC. If you do not have a default VPC, or if you do not specify a subnet ID, the request fails. For more information, see `Instance Types Available Only in a VPC <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-vpc.html#vpc-only-instance-types>`_ . 
 
* [EC2-VPC] All instances have a network interface with a primary private IPv4 address. If you don't specify this address, we choose one from the IPv4 range of your subnet. 
 
* Not all instance types support IPv6 addresses. For more information, see `Instance Types <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html>`_ . 
 
* If you don't specify a security group ID, we use the default security group. For more information, see `Security Groups <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-network-security.html>`_ . 
 
* If any of the AMIs have a product code attached for which the user has not subscribed, the request fails. 
 

 

To ensure faster instance launches, break up large requests into smaller batches. For example, create 5 separate launch requests for 100 instances each instead of 1 launch request for 500 instances.

 

An instance is ready for you to use when it's in the ``running`` state. You can check the state of your instance using  describe-instances . You can tag instances and EBS volumes during launch, after launch, or both. For more information, see  create-tags and `Tagging Your Amazon EC2 Resources <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html>`_ .

 

Linux instances have access to the public key of the key pair at boot. You can use this key to provide secure access to the instance. Amazon EC2 public images use this feature to provide secure access without passwords. For more information, see `Key Pairs <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

For troubleshooting, see `What To Do If An Instance Immediately Terminates <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_InstanceStraightToTerminated.html>`_ , and `Troubleshooting Connecting to Your Instance <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/TroubleshootingInstancesConnecting.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/RunInstances>`_


========
Synopsis
========

::

    run-instances
  [--block-device-mappings <value>]
  --image-id <value>
  [--instance-type <value>]
  [--ipv6-address-count <value>]
  [--ipv6-addresses <value>]
  [--kernel-id <value>]
  [--key-name <value>]
  [--monitoring <value>]
  [--placement <value>]
  [--ramdisk-id <value>]
  [--security-group-ids <value>]
  [--security-groups <value>]
  [--subnet-id <value>]
  [--user-data <value>]
  [--additional-info <value>]
  [--client-token <value>]
  [--disable-api-termination | --enable-api-termination]
  [--dry-run | --no-dry-run]
  [--ebs-optimized | --no-ebs-optimized]
  [--iam-instance-profile <value>]
  [--instance-initiated-shutdown-behavior <value>]
  [--network-interfaces <value>]
  [--private-ip-address <value>]
  [--tag-specifications <value>]
  [--count <value>]
  [--secondary-private-ip-addresses <value>]
  [--secondary-private-ip-address-count <value>]
  [--associate-public-ip-address | --no-associate-public-ip-address]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--block-device-mappings`` (list)


  The block device mapping.

   

  .. warning::

     

    Supplying both a snapshot ID and an encryption value as arguments for block-device mapping results in an error. This is because only blank volumes can be encrypted on start, and these are not created from a snapshot. If a snapshot is the basis for the volume, it contains data by definition and its encryption status cannot be changed using this action.

     

  



Shorthand Syntax::

    DeviceName=string,VirtualName=string,Ebs={Encrypted=boolean,DeleteOnTermination=boolean,Iops=integer,SnapshotId=string,VolumeSize=integer,VolumeType=string},NoDevice=string ...




JSON Syntax::

  [
    {
      "DeviceName": "string",
      "VirtualName": "string",
      "Ebs": {
        "Encrypted": true|false,
        "DeleteOnTermination": true|false,
        "Iops": integer,
        "SnapshotId": "string",
        "VolumeSize": integer,
        "VolumeType": "standard"|"io1"|"gp2"|"sc1"|"st1"
      },
      "NoDevice": "string"
    }
    ...
  ]



``--image-id`` (string)


  The ID of the AMI, which you can get by calling  describe-images .

  

``--instance-type`` (string)


  The instance type. For more information, see `Instance Types <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

   

  Default: ``m1.small``  

  

  Possible values:

  
  *   ``t1.micro``

  
  *   ``t2.nano``

  
  *   ``t2.micro``

  
  *   ``t2.small``

  
  *   ``t2.medium``

  
  *   ``t2.large``

  
  *   ``t2.xlarge``

  
  *   ``t2.2xlarge``

  
  *   ``m1.small``

  
  *   ``m1.medium``

  
  *   ``m1.large``

  
  *   ``m1.xlarge``

  
  *   ``m3.medium``

  
  *   ``m3.large``

  
  *   ``m3.xlarge``

  
  *   ``m3.2xlarge``

  
  *   ``m4.large``

  
  *   ``m4.xlarge``

  
  *   ``m4.2xlarge``

  
  *   ``m4.4xlarge``

  
  *   ``m4.10xlarge``

  
  *   ``m4.16xlarge``

  
  *   ``m2.xlarge``

  
  *   ``m2.2xlarge``

  
  *   ``m2.4xlarge``

  
  *   ``cr1.8xlarge``

  
  *   ``r3.large``

  
  *   ``r3.xlarge``

  
  *   ``r3.2xlarge``

  
  *   ``r3.4xlarge``

  
  *   ``r3.8xlarge``

  
  *   ``r4.large``

  
  *   ``r4.xlarge``

  
  *   ``r4.2xlarge``

  
  *   ``r4.4xlarge``

  
  *   ``r4.8xlarge``

  
  *   ``r4.16xlarge``

  
  *   ``x1.16xlarge``

  
  *   ``x1.32xlarge``

  
  *   ``i2.xlarge``

  
  *   ``i2.2xlarge``

  
  *   ``i2.4xlarge``

  
  *   ``i2.8xlarge``

  
  *   ``i3.large``

  
  *   ``i3.xlarge``

  
  *   ``i3.2xlarge``

  
  *   ``i3.4xlarge``

  
  *   ``i3.8xlarge``

  
  *   ``i3.16xlarge``

  
  *   ``hi1.4xlarge``

  
  *   ``hs1.8xlarge``

  
  *   ``c1.medium``

  
  *   ``c1.xlarge``

  
  *   ``c3.large``

  
  *   ``c3.xlarge``

  
  *   ``c3.2xlarge``

  
  *   ``c3.4xlarge``

  
  *   ``c3.8xlarge``

  
  *   ``c4.large``

  
  *   ``c4.xlarge``

  
  *   ``c4.2xlarge``

  
  *   ``c4.4xlarge``

  
  *   ``c4.8xlarge``

  
  *   ``cc1.4xlarge``

  
  *   ``cc2.8xlarge``

  
  *   ``g2.2xlarge``

  
  *   ``g2.8xlarge``

  
  *   ``g3.4xlarge``

  
  *   ``g3.8xlarge``

  
  *   ``g3.16xlarge``

  
  *   ``cg1.4xlarge``

  
  *   ``p2.xlarge``

  
  *   ``p2.8xlarge``

  
  *   ``p2.16xlarge``

  
  *   ``d2.xlarge``

  
  *   ``d2.2xlarge``

  
  *   ``d2.4xlarge``

  
  *   ``d2.8xlarge``

  
  *   ``f1.2xlarge``

  
  *   ``f1.16xlarge``

  

  

``--ipv6-address-count`` (integer)


  [EC2-VPC] A number of IPv6 addresses to associate with the primary network interface. Amazon EC2 chooses the IPv6 addresses from the range of your subnet. You cannot specify this option and the option to assign specific IPv6 addresses in the same request. You can specify this option if you've specified a minimum number of instances to launch.

  

``--ipv6-addresses`` (list)


  [EC2-VPC] Specify one or more IPv6 addresses from the range of the subnet to associate with the primary network interface. You cannot specify this option and the option to assign a number of IPv6 addresses in the same request. You cannot specify this option if you've specified a minimum number of instances to launch.

  



Shorthand Syntax::

    Ipv6Address=string ...




JSON Syntax::

  [
    {
      "Ipv6Address": "string"
    }
    ...
  ]



``--kernel-id`` (string)


  The ID of the kernel.

   

  .. warning::

     

    We recommend that you use PV-GRUB instead of kernels and RAM disks. For more information, see `PV-GRUB <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/UserProvidedkernels.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

     

  

``--key-name`` (string)


  The name of the key pair. You can create a key pair using  create-key-pair or  import-key-pair .

   

  .. warning::

     

    If you do not specify a key pair, you can't connect to the instance unless you choose an AMI that is configured to allow users another way to log in.

     

  

``--monitoring`` (structure)


  The monitoring for the instance.

  



Shorthand Syntax::

    Enabled=boolean




JSON Syntax::

  {
    "Enabled": true|false
  }



``--placement`` (structure)


  The placement for the instance.

  



Shorthand Syntax::

    AvailabilityZone=string,Affinity=string,GroupName=string,HostId=string,Tenancy=string,SpreadDomain=string




JSON Syntax::

  {
    "AvailabilityZone": "string",
    "Affinity": "string",
    "GroupName": "string",
    "HostId": "string",
    "Tenancy": "default"|"dedicated"|"host",
    "SpreadDomain": "string"
  }



``--ramdisk-id`` (string)


  The ID of the RAM disk.

   

  .. warning::

     

    We recommend that you use PV-GRUB instead of kernels and RAM disks. For more information, see `PV-GRUB <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/UserProvidedkernels.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

     

  

``--security-group-ids`` (list)


  One or more security group IDs. You can create a security group using  create-security-group .

   

  Default: Amazon EC2 uses the default security group.

  



Syntax::

  "string" "string" ...



``--security-groups`` (list)


  [EC2-Classic, default VPC] One or more security group names. For a nondefault VPC, you must use security group IDs instead.

   

  Default: Amazon EC2 uses the default security group.

  



Syntax::

  "string" "string" ...



``--subnet-id`` (string)


  [EC2-VPC] The ID of the subnet to launch the instance into.

  

``--user-data`` (string)


  The user data to make available to the instance. For more information, see `Running Commands on Your Linux Instance at Launch <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/user-data.html>`_ (Linux) and `Adding User Data <http://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ec2-instance-metadata.html#instancedata-add-user-data>`_ (Windows). If you are using an AWS SDK or command line tool, Base64-encoding is performed for you, and you can load the text from a file. Otherwise, you must provide Base64-encoded text.

  

``--additional-info`` (string)


  Reserved.

  

``--client-token`` (string)


  Unique, case-sensitive identifier you provide to ensure the idempotency of the request. For more information, see `Ensuring Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/Run_Instance_Idempotency.html>`_ .

   

  Constraints: Maximum 64 ASCII characters

  

``--disable-api-termination`` | ``--enable-api-termination`` (boolean)


  If you set this parameter to ``true`` , you can't terminate the instance using the Amazon EC2 console, CLI, or API; otherwise, you can. To change this attribute to ``false`` after launch, use  modify-instance-attribute . Alternatively, if you set ``InstanceInitiatedShutdownBehavior`` to ``terminate`` , you can terminate the instance by running the shutdown command from the instance.

   

  Default: ``false``  

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--ebs-optimized`` | ``--no-ebs-optimized`` (boolean)


  Indicates whether the instance is optimized for EBS I/O. This optimization provides dedicated throughput to Amazon EBS and an optimized configuration stack to provide optimal EBS I/O performance. This optimization isn't available with all instance types. Additional usage charges apply when using an EBS-optimized instance.

   

  Default: ``false``  

  

``--iam-instance-profile`` (structure)


  The IAM instance profile.

  



Shorthand Syntax::

    Arn=string,Name=string




JSON Syntax::

  {
    "Arn": "string",
    "Name": "string"
  }



``--instance-initiated-shutdown-behavior`` (string)


  Indicates whether an instance stops or terminates when you initiate shutdown from the instance (using the operating system command for system shutdown).

   

  Default: ``stop``  

  

  Possible values:

  
  *   ``stop``

  
  *   ``terminate``

  

  

``--network-interfaces`` (list)


  One or more network interfaces.

  



Shorthand Syntax::

    AssociatePublicIpAddress=boolean,DeleteOnTermination=boolean,Description=string,DeviceIndex=integer,Groups=string,string,Ipv6AddressCount=integer,Ipv6Addresses=[{Ipv6Address=string},{Ipv6Address=string}],NetworkInterfaceId=string,PrivateIpAddress=string,PrivateIpAddresses=[{Primary=boolean,PrivateIpAddress=string},{Primary=boolean,PrivateIpAddress=string}],SecondaryPrivateIpAddressCount=integer,SubnetId=string ...




JSON Syntax::

  [
    {
      "AssociatePublicIpAddress": true|false,
      "DeleteOnTermination": true|false,
      "Description": "string",
      "DeviceIndex": integer,
      "Groups": ["string", ...],
      "Ipv6AddressCount": integer,
      "Ipv6Addresses": [
        {
          "Ipv6Address": "string"
        }
        ...
      ],
      "NetworkInterfaceId": "string",
      "PrivateIpAddress": "string",
      "PrivateIpAddresses": [
        {
          "Primary": true|false,
          "PrivateIpAddress": "string"
        }
        ...
      ],
      "SecondaryPrivateIpAddressCount": integer,
      "SubnetId": "string"
    }
    ...
  ]



``--private-ip-address`` (string)


  [EC2-VPC] The primary IPv4 address. You must specify a value from the IPv4 address range of the subnet.

   

  Only one private IP address can be designated as primary. You can't specify this option if you've specified the option to designate a private IP address as the primary IP address in a network interface specification. You cannot specify this option if you're launching more than one instance in the request.

  

``--tag-specifications`` (list)


  The tags to apply to the resources during launch. You can tag instances and volumes. The specified tags are applied to all instances or volumes that are created during launch.

  



Shorthand Syntax::

    ResourceType=string,Tags=[{Key=string,Value=string},{Key=string,Value=string}] ...




JSON Syntax::

  [
    {
      "ResourceType": "customer-gateway"|"dhcp-options"|"image"|"instance"|"internet-gateway"|"network-acl"|"network-interface"|"reserved-instances"|"route-table"|"snapshot"|"spot-instances-request"|"subnet"|"security-group"|"volume"|"vpc"|"vpn-connection"|"vpn-gateway",
      "Tags": [
        {
          "Key": "string",
          "Value": "string"
        }
        ...
      ]
    }
    ...
  ]



``--count`` (string)
 

  Number of instances to launch. If a single number is provided, it is assumed to be the minimum to launch (defaults to 1). If a range is provided in the form ``min:max`` then the first number is interpreted as the minimum number of instances to launch and the second is interpreted as the maximum number of instances to launch.

  

``--secondary-private-ip-addresses`` (string)
[EC2-VPC] A secondary private IP address for the network interface or instance. You can specify this multiple times to assign multiple secondary IP addresses. If you want additional private IP addresses but do not need a specific address, use the --secondary-private-ip-address-count option.

``--secondary-private-ip-address-count`` (string)
[EC2-VPC] The number of secondary IP addresses to assign to the network interface or instance.

``--associate-public-ip-address`` | ``--no-associate-public-ip-address`` (boolean)
[EC2-VPC] If specified a public IP address will be assigned to the new instance in a VPC.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To launch an instance in EC2-Classic**

This example launches a single instance of type ``c3.large``.

The key pair and security group, named ``MyKeyPair`` and ``MySecurityGroup``, must exist.

Command::

  aws ec2 run-instances --image-id ami-1a2b3c4d --count 1 --instance-type c3.large --key-name MyKeyPair --security-groups MySecurityGroup

Output::

  {
      "OwnerId": "123456789012",
      "ReservationId": "r-08626e73c547023b1",
      "Groups": [
          {
              "GroupName": "MySecurityGroup",
              "GroupId": "sg-903004f8"
          }
      ],
      "Instances": [
          {
              "Monitoring": {
                  "State": "disabled"
              },
              "PublicDnsName": null,
              "RootDeviceType": "ebs",
              "State": {
                  "Code": 0,
                  "Name": "pending"
              },
              "EbsOptimized": false,
              "LaunchTime": "2013-07-19T02:42:39.000Z",
              "ProductCodes": [],
              "StateTransitionReason": null, 
              "InstanceId": "i-1234567890abcdef0",
              "ImageId": "ami-1a2b3c4d",
              "PrivateDnsName": null,
              "KeyName": "MyKeyPair",
              "SecurityGroups": [
                  {
                      "GroupName": "MySecurityGroup",
                      "GroupId": "sg-903004f8"
                  }
              ],
              "ClientToken": null,
              "InstanceType": "c3.large",
              "NetworkInterfaces": [],
              "Placement": {
                  "Tenancy": "default",
                  "GroupName": null,
                  "AvailabilityZone": "us-east-1b"
              },
              "Hypervisor": "xen",
              "BlockDeviceMappings": [],
              "Architecture": "x86_64",
              "StateReason": {
                  "Message": "pending",
                  "Code": "pending"
              },
              "RootDeviceName": "/dev/sda1",
              "VirtualizationType": "hvm",
              "AmiLaunchIndex": 0
          }
      ]
  }

**To launch an instance in EC2-VPC**

This example launches a single instance of type ``t2.micro`` into the specified subnet.

The key pair named ``MyKeyPair`` and the security group sg-903004f8 must exist.

Command::

  aws ec2 run-instances --image-id ami-abc12345 --count 1 --instance-type t2.micro --key-name MyKeyPair --security-group-ids sg-903004f8 --subnet-id subnet-6e7f829e

Output::

  {
      "OwnerId": "123456789012",
      "ReservationId": "r-08626e73c547023b2",
      "Groups": [],
      "Instances": [
          {
              "Monitoring": {
                  "State": "disabled"
              },
              "PublicDnsName": null,
              "RootDeviceType": "ebs",
              "State": {
                  "Code": 0,
                  "Name": "pending"
              },
              "EbsOptimized": false,
              "LaunchTime": "2013-07-19T02:42:39.000Z",
              "PrivateIpAddress": "10.0.1.114",
              "ProductCodes": [],
              "VpcId": "vpc-1a2b3c4d",
              "InstanceId": "i-1234567890abcdef5",
              "ImageId": "ami-abc12345",
              "PrivateDnsName": "ip-10-0-1-114.ec2.internal",
              "KeyName": "MyKeyPair",
              "SecurityGroups": [
                  {
                      "GroupName": "MySecurityGroup",
                      "GroupId": "sg-903004f8"
                  }
              ],
              "ClientToken": null,
              "SubnetId": "subnet-6e7f829e",
              "InstanceType": "t2.micro",
              "NetworkInterfaces": [
                  {
                      "Status": "in-use",
                      "MacAddress": "0e:ad:05:3b:60:52",
                      "SourceDestCheck": true,
                      "VpcId": "vpc-1a2b3c4d",
                      "Description": "null",
                      "NetworkInterfaceId": "eni-a7edb1c9",
                      "PrivateIpAddresses": [
                          {
                              "PrivateDnsName": "ip-10-0-1-114.ec2.internal",
                              "Primary": true,
                              "PrivateIpAddress": "10.0.1.114"
                          }
                      ],
                      "Ipv6Addresses": [],
                      "PrivateDnsName": "ip-10-0-1-114.ec2.internal",
                      "Attachment": {
                          "Status": "attached",
                          "DeviceIndex": 0,
                          "DeleteOnTermination": true,
                          "AttachmentId": "eni-attach-52193138",
                          "AttachTime": "2013-07-19T02:42:39.000Z"
                      },
                      "Groups": [
                          {
                              "GroupName": "MySecurityGroup",
                              "GroupId": "sg-903004f8"
                          }
                      ],
                      "SubnetId": "subnet-6e7f829e",
                      "OwnerId": "123456789012",
                      "PrivateIpAddress": "10.0.1.114"
                  }
              ],
              "SourceDestCheck": true,
              "Placement": {
                  "Tenancy": "default",
                  "GroupName": null,
                  "AvailabilityZone": "us-east-1b"
              },
              "Hypervisor": "xen",
              "BlockDeviceMappings": [],
              "Architecture": "x86_64",
              "StateReason": {
                  "Message": "pending",
                  "Code": "pending"
              },
              "RootDeviceName": "/dev/sda1",
              "VirtualizationType": "hvm",
              "AmiLaunchIndex": 0
          }
      ]
  }

The following example requests a public IP address for an instance that you're launching into a nondefault subnet:

Command::

  aws ec2 run-instances --image-id ami-c3b8d6aa --count 1 --instance-type t2.medium --key-name MyKeyPair --security-group-ids sg-903004f8 --subnet-id subnet-6e7f829e --associate-public-ip-address

**To launch an instance using a block device mapping**

Add the following parameter to your ``run-instances`` command to specify block devices::

  --block-device-mappings file://mapping.json

To add an Amazon EBS volume with the device name ``/dev/sdh`` and a volume size of 100, specify the following in mapping.json::

  [
    {
      "DeviceName": "/dev/sdh",
      "Ebs": {
        "VolumeSize": 100
      }
    }
  ]

To add ``ephemeral1`` as an instance store volume with the device name ``/dev/sdc``, specify the following in mapping.json::

  [
    {
      "DeviceName": "/dev/sdc",
      "VirtualName": "ephemeral1"
    }
  ]

To omit a device specified by the AMI used to launch the instance (for example, ``/dev/sdf``), specify the following in mapping.json::

  [
    {
      "DeviceName": "/dev/sdf",
      "NoDevice": ""
    }
  ]

You can view only the Amazon EBS volumes in your block device mapping using the console or the ``describe-instances`` command. To view all volumes, including the instance store volumes, use the following command.

Command::

  curl http://169.254.169.254/latest/meta-data/block-device-mapping/

Output::

  ami
  ephemeral1

Note that ``ami`` represents the root volume. To get details about the instance store volume ``ephemeral1``, use the following command.

Command::

  curl http://169.254.169.254/latest/meta-data/block-device-mapping/ephemeral1

Output::

  sdc

**To launch an instance with a modified block device mapping**

You can change individual characteristics of existing AMI block device mappings to suit your needs. Perhaps you want to use an existing AMI, but you want a larger root volume than the usual 8 GiB. Or, you would like to use a General Purpose (SSD) volume for an AMI that currently uses a Magnetic volume.

Use the ``describe-images`` command with the image ID of the AMI you want to use to find its existing block device mapping. You should see a block device mapping in the output::

  {
    "DeviceName": "/dev/sda1",
    "Ebs": {
      "DeleteOnTermination": true,
      "SnapshotId": "snap-1234567890abcdef0",
      "VolumeSize": 8,
      "VolumeType": "standard",
      "Encrypted": false
    }
  }

You can modify the above mapping by changing the individual parameters. For example, to launch an instance with a modified block device mapping, add the following parameter to your ``run-instances`` command to change the above mapping's volume size and type::

  --block-device-mappings file://mapping.json

Where mapping.json contains the following::

  [
    {
      "DeviceName": "/dev/sda1",
      "Ebs": {
        "DeleteOnTermination": true,
        "SnapshotId": "snap-1234567890abcdef0", 
        "VolumeSize": 100,
        "VolumeType": "gp2"
      }
    }
  ]

**To launch an instance with user data**

You can launch an instance and specify user data that performs instance configuration, or that runs a script. The user data needs to be passed as normal string, base64 encoding is handled internally. The following example passes user data in a file called ``my_script.txt`` that contains a configuration script for your instance. The script runs at launch.

Command::

  aws ec2 run-instances --image-id ami-abc1234 --count 1 --instance-type m4.large --key-name keypair --user-data file://my_script.txt --subnet-id subnet-abcd1234 --security-group-ids sg-abcd1234 

For more information about launching instances, see `Using Amazon EC2 Instances`_ in the *AWS Command Line Interface User Guide*.

.. _`Using Amazon EC2 Instances`: http://docs.aws.amazon.com/cli/latest/userguide/cli-ec2-launch.html

**To launch an instance with an instance profile**

This example shows the use of the ``iam-instance-profile`` option to specify an `IAM instance profile`_ by name.

.. _`IAM instance profile`: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/iam-roles-for-amazon-ec2.html

Command::

  aws ec2 run-instances --iam-instance-profile Name=MyInstanceProfile --image-id ami-1a2b3c4d --count 1 --instance-type t2.micro --key-name MyKeyPair --security-groups MySecurityGroup

**To launch an instance with tags**

You can launch an instance and specify tags for the instance, volumes, or both. The following example applies a tag with a key of ``webserver`` and value of ``production`` to the instance. The command also applies a tag with a key of ``cost-center`` and a value of ``cc123`` to any EBS volume that's created (in this case, the root volume).

Command::

  aws ec2 run-instances --image-id ami-abc12345 --count 1 --instance-type t2.micro --key-name MyKeyPair --subnet-id subnet-6e7f829e --tag-specifications 'ResourceType=instance,Tags=[{Key=webserver,Value=production}]' 'ResourceType=volume,Tags=[{Key=cost-center,Value=cc123}]' 

======
Output
======

Groups -> (list)

  

  [EC2-Classic only] One or more security groups.

  

  (structure)

    

    Describes a security group.

    

    GroupName -> (string)

      

      The name of the security group.

      

      

    GroupId -> (string)

      

      The ID of the security group.

      

      

    

  

Instances -> (list)

  

  One or more instances.

  

  (structure)

    

    Describes an instance.

    

    AmiLaunchIndex -> (integer)

      

      The AMI launch index, which can be used to find this instance in the launch group.

      

      

    ImageId -> (string)

      

      The ID of the AMI used to launch the instance.

      

      

    InstanceId -> (string)

      

      The ID of the instance.

      

      

    InstanceType -> (string)

      

      The instance type.

      

      

    KernelId -> (string)

      

      The kernel associated with this instance, if applicable.

      

      

    KeyName -> (string)

      

      The name of the key pair, if this instance was launched with an associated key pair.

      

      

    LaunchTime -> (timestamp)

      

      The time the instance was launched.

      

      

    Monitoring -> (structure)

      

      The monitoring for the instance.

      

      State -> (string)

        

        Indicates whether detailed monitoring is enabled. Otherwise, basic monitoring is enabled.

        

        

      

    Placement -> (structure)

      

      The location where the instance launched, if applicable.

      

      AvailabilityZone -> (string)

        

        The Availability Zone of the instance.

        

        

      Affinity -> (string)

        

        The affinity setting for the instance on the Dedicated Host. This parameter is not supported for the  import-instance command.

        

        

      GroupName -> (string)

        

        The name of the placement group the instance is in (for cluster compute instances).

        

        

      HostId -> (string)

        

        The ID of the Dedicated Host on which the instance resides. This parameter is not supported for the  import-instance command.

        

        

      Tenancy -> (string)

        

        The tenancy of the instance (if the instance is running in a VPC). An instance with a tenancy of ``dedicated`` runs on single-tenant hardware. The ``host`` tenancy is not supported for the  import-instance command.

        

        

      SpreadDomain -> (string)

        

        Reserved for future use.

        

        

      

    Platform -> (string)

      

      The value is ``Windows`` for Windows instances; otherwise blank.

      

      

    PrivateDnsName -> (string)

      

      (IPv4 only) The private DNS hostname name assigned to the instance. This DNS hostname can only be used inside the Amazon EC2 network. This name is not available until the instance enters the ``running`` state. 

       

      [EC2-VPC] The Amazon-provided DNS server will resolve Amazon-provided private DNS hostnames if you've enabled DNS resolution and DNS hostnames in your VPC. If you are not using the Amazon-provided DNS server in your VPC, your custom domain name servers must resolve the hostname as appropriate.

      

      

    PrivateIpAddress -> (string)

      

      The private IPv4 address assigned to the instance.

      

      

    ProductCodes -> (list)

      

      The product codes attached to this instance, if applicable.

      

      (structure)

        

        Describes a product code.

        

        ProductCodeId -> (string)

          

          The product code.

          

          

        ProductCodeType -> (string)

          

          The type of product code.

          

          

        

      

    PublicDnsName -> (string)

      

      (IPv4 only) The public DNS name assigned to the instance. This name is not available until the instance enters the ``running`` state. For EC2-VPC, this name is only available if you've enabled DNS hostnames for your VPC.

      

      

    PublicIpAddress -> (string)

      

      The public IPv4 address assigned to the instance, if applicable.

      

      

    RamdiskId -> (string)

      

      The RAM disk associated with this instance, if applicable.

      

      

    State -> (structure)

      

      The current state of the instance.

      

      Code -> (integer)

        

        The low byte represents the state. The high byte is an opaque internal value and should be ignored.

         

         
        * ``0`` : ``pending``   
         
        * ``16`` : ``running``   
         
        * ``32`` : ``shutting-down``   
         
        * ``48`` : ``terminated``   
         
        * ``64`` : ``stopping``   
         
        * ``80`` : ``stopped``   
         

        

        

      Name -> (string)

        

        The current state of the instance.

        

        

      

    StateTransitionReason -> (string)

      

      The reason for the most recent state transition. This might be an empty string.

      

      

    SubnetId -> (string)

      

      [EC2-VPC] The ID of the subnet in which the instance is running.

      

      

    VpcId -> (string)

      

      [EC2-VPC] The ID of the VPC in which the instance is running.

      

      

    Architecture -> (string)

      

      The architecture of the image.

      

      

    BlockDeviceMappings -> (list)

      

      Any block device mapping entries for the instance.

      

      (structure)

        

        Describes a block device mapping.

        

        DeviceName -> (string)

          

          The device name exposed to the instance (for example, ``/dev/sdh`` or ``xvdh`` ).

          

          

        Ebs -> (structure)

          

          Parameters used to automatically set up EBS volumes when the instance is launched.

          

          AttachTime -> (timestamp)

            

            The time stamp when the attachment initiated.

            

            

          DeleteOnTermination -> (boolean)

            

            Indicates whether the volume is deleted on instance termination.

            

            

          Status -> (string)

            

            The attachment state.

            

            

          VolumeId -> (string)

            

            The ID of the EBS volume.

            

            

          

        

      

    ClientToken -> (string)

      

      The idempotency token you provided when you launched the instance, if applicable.

      

      

    EbsOptimized -> (boolean)

      

      Indicates whether the instance is optimized for EBS I/O. This optimization provides dedicated throughput to Amazon EBS and an optimized configuration stack to provide optimal I/O performance. This optimization isn't available with all instance types. Additional usage charges apply when using an EBS Optimized instance.

      

      

    EnaSupport -> (boolean)

      

      Specifies whether enhanced networking with ENA is enabled.

      

      

    Hypervisor -> (string)

      

      The hypervisor type of the instance.

      

      

    IamInstanceProfile -> (structure)

      

      The IAM instance profile associated with the instance, if applicable.

      

      Arn -> (string)

        

        The Amazon Resource Name (ARN) of the instance profile.

        

        

      Id -> (string)

        

        The ID of the instance profile.

        

        

      

    InstanceLifecycle -> (string)

      

      Indicates whether this is a Spot instance or a Scheduled Instance.

      

      

    NetworkInterfaces -> (list)

      

      [EC2-VPC] One or more network interfaces for the instance.

      

      (structure)

        

        Describes a network interface.

        

        Association -> (structure)

          

          The association information for an Elastic IPv4 associated with the network interface.

          

          IpOwnerId -> (string)

            

            The ID of the owner of the Elastic IP address.

            

            

          PublicDnsName -> (string)

            

            The public DNS name.

            

            

          PublicIp -> (string)

            

            The public IP address or Elastic IP address bound to the network interface.

            

            

          

        Attachment -> (structure)

          

          The network interface attachment.

          

          AttachTime -> (timestamp)

            

            The time stamp when the attachment initiated.

            

            

          AttachmentId -> (string)

            

            The ID of the network interface attachment.

            

            

          DeleteOnTermination -> (boolean)

            

            Indicates whether the network interface is deleted when the instance is terminated.

            

            

          DeviceIndex -> (integer)

            

            The index of the device on the instance for the network interface attachment.

            

            

          Status -> (string)

            

            The attachment state.

            

            

          

        Description -> (string)

          

          The description.

          

          

        Groups -> (list)

          

          One or more security groups.

          

          (structure)

            

            Describes a security group.

            

            GroupName -> (string)

              

              The name of the security group.

              

              

            GroupId -> (string)

              

              The ID of the security group.

              

              

            

          

        Ipv6Addresses -> (list)

          

          One or more IPv6 addresses associated with the network interface.

          

          (structure)

            

            Describes an IPv6 address.

            

            Ipv6Address -> (string)

              

              The IPv6 address.

              

              

            

          

        MacAddress -> (string)

          

          The MAC address.

          

          

        NetworkInterfaceId -> (string)

          

          The ID of the network interface.

          

          

        OwnerId -> (string)

          

          The ID of the AWS account that created the network interface.

          

          

        PrivateDnsName -> (string)

          

          The private DNS name.

          

          

        PrivateIpAddress -> (string)

          

          The IPv4 address of the network interface within the subnet.

          

          

        PrivateIpAddresses -> (list)

          

          One or more private IPv4 addresses associated with the network interface.

          

          (structure)

            

            Describes a private IPv4 address.

            

            Association -> (structure)

              

              The association information for an Elastic IP address for the network interface.

              

              IpOwnerId -> (string)

                

                The ID of the owner of the Elastic IP address.

                

                

              PublicDnsName -> (string)

                

                The public DNS name.

                

                

              PublicIp -> (string)

                

                The public IP address or Elastic IP address bound to the network interface.

                

                

              

            Primary -> (boolean)

              

              Indicates whether this IPv4 address is the primary private IP address of the network interface.

              

              

            PrivateDnsName -> (string)

              

              The private IPv4 DNS name.

              

              

            PrivateIpAddress -> (string)

              

              The private IPv4 address of the network interface.

              

              

            

          

        SourceDestCheck -> (boolean)

          

          Indicates whether to validate network traffic to or from this network interface.

          

          

        Status -> (string)

          

          The status of the network interface.

          

          

        SubnetId -> (string)

          

          The ID of the subnet.

          

          

        VpcId -> (string)

          

          The ID of the VPC.

          

          

        

      

    RootDeviceName -> (string)

      

      The root device name (for example, ``/dev/sda1`` or ``/dev/xvda`` ).

      

      

    RootDeviceType -> (string)

      

      The root device type used by the AMI. The AMI can use an EBS volume or an instance store volume.

      

      

    SecurityGroups -> (list)

      

      One or more security groups for the instance.

      

      (structure)

        

        Describes a security group.

        

        GroupName -> (string)

          

          The name of the security group.

          

          

        GroupId -> (string)

          

          The ID of the security group.

          

          

        

      

    SourceDestCheck -> (boolean)

      

      Specifies whether to enable an instance launched in a VPC to perform NAT. This controls whether source/destination checking is enabled on the instance. A value of ``true`` means checking is enabled, and ``false`` means checking is disabled. The value must be ``false`` for the instance to perform NAT. For more information, see `NAT Instances <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_NAT_Instance.html>`_ in the *Amazon Virtual Private Cloud User Guide* .

      

      

    SpotInstanceRequestId -> (string)

      

      If the request is a Spot instance request, the ID of the request.

      

      

    SriovNetSupport -> (string)

      

      Specifies whether enhanced networking with the Intel 82599 Virtual Function interface is enabled.

      

      

    StateReason -> (structure)

      

      The reason for the most recent state transition.

      

      Code -> (string)

        

        The reason code for the state change.

        

        

      Message -> (string)

        

        The message for the state change.

         

         
        * ``Server.InsufficientInstanceCapacity`` : There was insufficient instance capacity to satisfy the launch request. 
         
        * ``Server.InternalError`` : An internal error occurred during instance launch, resulting in termination. 
         
        * ``Server.ScheduledStop`` : The instance was stopped due to a scheduled retirement. 
         
        * ``Server.SpotInstanceTermination`` : A Spot instance was terminated due to an increase in the market price. 
         
        * ``Client.InternalError`` : A client error caused the instance to terminate on launch. 
         
        * ``Client.InstanceInitiatedShutdown`` : The instance was shut down using the ``shutdown -h`` command from the instance. 
         
        * ``Client.UserInitiatedShutdown`` : The instance was shut down using the Amazon EC2 API. 
         
        * ``Client.VolumeLimitExceeded`` : The limit on the number of EBS volumes or total storage was exceeded. Decrease usage or request an increase in your limits. 
         
        * ``Client.InvalidSnapshot.NotFound`` : The specified snapshot was not found. 
         

        

        

      

    Tags -> (list)

      

      Any tags assigned to the instance.

      

      (structure)

        

        Describes a tag.

        

        Key -> (string)

          

          The key of the tag.

           

          Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:``  

          

          

        Value -> (string)

          

          The value of the tag.

           

          Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

          

          

        

      

    VirtualizationType -> (string)

      

      The virtualization type of the instance.

      

      

    

  

OwnerId -> (string)

  

  The ID of the AWS account that owns the reservation.

  

  

RequesterId -> (string)

  

  The ID of the requester that launched the instances on your behalf (for example, AWS Management Console or Auto Scaling).

  

  

ReservationId -> (string)

  

  The ID of the reservation.

  

  

