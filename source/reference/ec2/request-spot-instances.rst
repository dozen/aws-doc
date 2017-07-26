[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 request-spot-instances:


**********************
request-spot-instances
**********************



===========
Description
===========



Creates a Spot instance request. Spot instances are instances that Amazon EC2 launches when the bid price that you specify exceeds the current Spot price. Amazon EC2 periodically sets the Spot price based on available Spot Instance capacity and current Spot instance requests. For more information, see `Spot Instance Requests <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-requests.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/RequestSpotInstances>`_


========
Synopsis
========

::

    request-spot-instances
  [--availability-zone-group <value>]
  [--block-duration-minutes <value>]
  [--client-token <value>]
  [--dry-run | --no-dry-run]
  [--instance-count <value>]
  [--launch-group <value>]
  [--launch-specification <value>]
  --spot-price <value>
  [--type <value>]
  [--valid-from <value>]
  [--valid-until <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--availability-zone-group`` (string)


  The user-specified name for a logical grouping of bids.

   

  When you specify an Availability Zone group in a Spot Instance request, all Spot instances in the request are launched in the same Availability Zone. Instance proximity is maintained with this parameter, but the choice of Availability Zone is not. The group applies only to bids for Spot Instances of the same instance type. Any additional Spot instance requests that are specified with the same Availability Zone group name are launched in that same Availability Zone, as long as at least one instance from the group is still active.

   

  If there is no active instance running in the Availability Zone group that you specify for a new Spot instance request (all instances are terminated, the bid is expired, or the bid falls below current market), then Amazon EC2 launches the instance in any Availability Zone where the constraint can be met. Consequently, the subsequent set of Spot instances could be placed in a different zone from the original request, even if you specified the same Availability Zone group.

   

  Default: Instances are launched in any available Availability Zone.

  

``--block-duration-minutes`` (integer)


  The required duration for the Spot instances (also known as Spot blocks), in minutes. This value must be a multiple of 60 (60, 120, 180, 240, 300, or 360).

   

  The duration period starts as soon as your Spot instance receives its instance ID. At the end of the duration period, Amazon EC2 marks the Spot instance for termination and provides a Spot instance termination notice, which gives the instance a two-minute warning before it terminates.

   

  Note that you can't specify an Availability Zone group or a launch group if you specify a duration.

  

``--client-token`` (string)


  Unique, case-sensitive identifier that you provide to ensure the idempotency of the request. For more information, see `How to Ensure Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Run_Instance_Idempotency.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instance-count`` (integer)


  The maximum number of Spot instances to launch.

   

  Default: 1

  

``--launch-group`` (string)


  The instance launch group. Launch groups are Spot instances that launch together and terminate together.

   

  Default: Instances are launched and terminated individually

  

``--launch-specification`` (structure)


  The launch specification.

  



JSON Syntax::

  {
    "SecurityGroupIds": ["string", ...],
    "SecurityGroups": ["string", ...],
    "AddressingType": "string",
    "BlockDeviceMappings": [
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
    ],
    "EbsOptimized": true|false,
    "IamInstanceProfile": {
      "Arn": "string",
      "Name": "string"
    },
    "ImageId": "string",
    "InstanceType": "t1.micro"|"t2.nano"|"t2.micro"|"t2.small"|"t2.medium"|"t2.large"|"t2.xlarge"|"t2.2xlarge"|"m1.small"|"m1.medium"|"m1.large"|"m1.xlarge"|"m3.medium"|"m3.large"|"m3.xlarge"|"m3.2xlarge"|"m4.large"|"m4.xlarge"|"m4.2xlarge"|"m4.4xlarge"|"m4.10xlarge"|"m4.16xlarge"|"m2.xlarge"|"m2.2xlarge"|"m2.4xlarge"|"cr1.8xlarge"|"r3.large"|"r3.xlarge"|"r3.2xlarge"|"r3.4xlarge"|"r3.8xlarge"|"r4.large"|"r4.xlarge"|"r4.2xlarge"|"r4.4xlarge"|"r4.8xlarge"|"r4.16xlarge"|"x1.16xlarge"|"x1.32xlarge"|"i2.xlarge"|"i2.2xlarge"|"i2.4xlarge"|"i2.8xlarge"|"i3.large"|"i3.xlarge"|"i3.2xlarge"|"i3.4xlarge"|"i3.8xlarge"|"i3.16xlarge"|"hi1.4xlarge"|"hs1.8xlarge"|"c1.medium"|"c1.xlarge"|"c3.large"|"c3.xlarge"|"c3.2xlarge"|"c3.4xlarge"|"c3.8xlarge"|"c4.large"|"c4.xlarge"|"c4.2xlarge"|"c4.4xlarge"|"c4.8xlarge"|"cc1.4xlarge"|"cc2.8xlarge"|"g2.2xlarge"|"g2.8xlarge"|"g3.4xlarge"|"g3.8xlarge"|"g3.16xlarge"|"cg1.4xlarge"|"p2.xlarge"|"p2.8xlarge"|"p2.16xlarge"|"d2.xlarge"|"d2.2xlarge"|"d2.4xlarge"|"d2.8xlarge"|"f1.2xlarge"|"f1.16xlarge",
    "KernelId": "string",
    "KeyName": "string",
    "Monitoring": {
      "Enabled": true|false
    },
    "NetworkInterfaces": [
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
    ],
    "Placement": {
      "AvailabilityZone": "string",
      "GroupName": "string",
      "Tenancy": "default"|"dedicated"|"host"
    },
    "RamdiskId": "string",
    "SubnetId": "string",
    "UserData": "string"
  }



``--spot-price`` (string)


  The maximum hourly price (bid) for any Spot instance launched to fulfill the request.

  

``--type`` (string)


  The Spot instance request type.

   

  Default: ``one-time``  

  

  Possible values:

  
  *   ``one-time``

  
  *   ``persistent``

  

  

``--valid-from`` (timestamp)


  The start date of the request. If this is a one-time request, the request becomes active at this date and time and remains active until all instances launch, the request expires, or the request is canceled. If the request is persistent, the request becomes active at this date and time and remains active until it expires or is canceled.

   

  Default: The request is effective indefinitely.

  

``--valid-until`` (timestamp)


  The end date of the request. If this is a one-time request, the request remains active until all instances launch, the request is canceled, or this date is reached. If the request is persistent, it remains active until it is canceled or this date and time is reached.

   

  Default: The request is effective indefinitely.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To request Spot Instances**

This example command creates a one-time Spot Instance request for five instances in the specified Availability Zone.
If your account supports EC2-VPC only, Amazon EC2 launches the instances in the default subnet of the specified Availability Zone.
If your account supports EC2-Classic, Amazon EC2 launches the instances in EC2-Classic in the specified Availability Zone.

Command::

  aws ec2 request-spot-instances --spot-price "0.03" --instance-count 5 --type "one-time" --launch-specification file://specification.json

Specification.json::
  
  {
    "ImageId": "ami-1a2b3c4d",
    "KeyName": "my-key-pair",
    "SecurityGroupIds": [ "sg-1a2b3c4d" ],
    "InstanceType": "m3.medium",
    "Placement": {
      "AvailabilityZone": "us-west-2a"
    },
    "IamInstanceProfile": {
        "Arn": "arn:aws:iam::123456789012:instance-profile/my-iam-role"
    }
  }

Output::

  {
    "SpotInstanceRequests": [
        {
            "Status": {
                "UpdateTime": "2014-03-25T20:54:21.000Z",
                "Code": "pending-evaluation",
                "Message": "Your Spot request has been submitted for review, and is pending evaluation."
            },
            "ProductDescription": "Linux/UNIX",
            "SpotInstanceRequestId": "sir-df6f405d",
            "State": "open",
            "LaunchSpecification": {
                "Placement": {
                    "AvailabilityZone": "us-west-2a"
                },
                "ImageId": "ami-1a2b3c4d",
                "KeyName": "my-key-pair",
                "SecurityGroups": [
                    {
                        "GroupName": "my-security-group",
                        "GroupId": "sg-1a2b3c4d"
                    }
                ],
                "Monitoring": {
                    "Enabled": false
                },
                "IamInstanceProfile": {
                    "Arn": "arn:aws:iam::123456789012:instance-profile/my-iam-role"
                },
                "InstanceType": "m3.medium"
            },
            "Type": "one-time",
            "CreateTime": "2014-03-25T20:54:20.000Z",
            "SpotPrice": "0.050000"
        },
        ...
    ]
  }

This example command creates a one-time Spot Instance request for five instances in the specified subnet.
Amazon EC2 launches the instances in the specified subnet. If the VPC is a nondefault VPC, the instances
do not receive a public IP address by default.

Command::

  aws ec2 request-spot-instances --spot-price "0.050" --instance-count 5 --type "one-time" --launch-specification file://specification.json
  
Specification.json::

  {
    "ImageId": "ami-1a2b3c4d",
    "SecurityGroupIds": [ "sg-1a2b3c4d" ],
    "InstanceType": "m3.medium",
    "SubnetId": "subnet-1a2b3c4d",
    "IamInstanceProfile": {
        "Arn": "arn:aws:iam::123456789012:instance-profile/my-iam-role"
    }
  }

Output::

  {
    "SpotInstanceRequests": [
        {
            "Status": {
               "UpdateTime": "2014-03-25T22:21:58.000Z",
               "Code": "pending-evaluation",
               "Message": "Your Spot request has been submitted for review, and is pending evaluation."
            },
            "ProductDescription": "Linux/UNIX",
            "SpotInstanceRequestId": "sir-df6f405d",
            "State": "open",
            "LaunchSpecification": {
               "Placement": {
                   "AvailabilityZone": "us-west-2a"
               }
               "ImageId": "ami-1a2b3c4d"
               "SecurityGroups": [
                   {
                       "GroupName": "my-security-group",
                       "GroupID": "sg-1a2b3c4d"
                   }
               ]
               "SubnetId": "subnet-1a2b3c4d",
               "Monitoring": {
                   "Enabled": false
               },
               "IamInstanceProfile": {
                   "Arn": "arn:aws:iam::123456789012:instance-profile/my-iam-role"
               },
               "InstanceType": "m3.medium",
           },
           "Type": "one-time",
           "CreateTime": "2014-03-25T22:21:58.000Z",
           "SpotPrice": "0.050000"
        },
        ...
    ]
  }

This example assigns a public IP address to the Spot Instances that you launch in a nondefault VPC.
Note that when you specify a network interface, you must include the subnet ID and security group ID
using the network interface.

Command::

  aws ec2 request-spot-instances --spot-price "0.050" --instance-count 1 --type "one-time" --launch-specification file://specification.json

Specification.json::
  
  {
    "ImageId": "ami-1a2b3c4d",
    "KeyName": "my-key-pair",
    "InstanceType": "m3.medium",
    "NetworkInterfaces": [
      {
        "DeviceIndex": 0,
        "SubnetId": "subnet-1a2b3c4d",
        "Groups": [ "sg-1a2b3c4d" ],
        "AssociatePublicIpAddress": true
      }
    ],
    "IamInstanceProfile": {
        "Arn": "arn:aws:iam::123456789012:instance-profile/my-iam-role"
    }
  }


======
Output
======

SpotInstanceRequests -> (list)

  

  One or more Spot instance requests.

  

  (structure)

    

    Describes a Spot instance request.

    

    ActualBlockHourlyPrice -> (string)

      

      If you specified a duration and your Spot instance request was fulfilled, this is the fixed hourly price in effect for the Spot instance while it runs.

      

      

    AvailabilityZoneGroup -> (string)

      

      The Availability Zone group. If you specify the same Availability Zone group for all Spot instance requests, all Spot instances are launched in the same Availability Zone.

      

      

    BlockDurationMinutes -> (integer)

      

      The duration for the Spot instance, in minutes.

      

      

    CreateTime -> (timestamp)

      

      The date and time when the Spot instance request was created, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z).

      

      

    Fault -> (structure)

      

      The fault codes for the Spot instance request, if any.

      

      Code -> (string)

        

        The reason code for the Spot instance state change.

        

        

      Message -> (string)

        

        The message for the Spot instance state change.

        

        

      

    InstanceId -> (string)

      

      The instance ID, if an instance has been launched to fulfill the Spot instance request.

      

      

    LaunchGroup -> (string)

      

      The instance launch group. Launch groups are Spot instances that launch together and terminate together.

      

      

    LaunchSpecification -> (structure)

      

      Additional information for launching instances.

      

      UserData -> (string)

        

        The user data to make available to the instances. If you are using an AWS SDK or command line tool, Base64-encoding is performed for you, and you can load the text from a file. Otherwise, you must provide Base64-encoded text.

        

        

      SecurityGroups -> (list)

        

        One or more security groups. When requesting instances in a VPC, you must specify the IDs of the security groups. When requesting instances in EC2-Classic, you can specify the names or the IDs of the security groups.

        

        (structure)

          

          Describes a security group.

          

          GroupName -> (string)

            

            The name of the security group.

            

            

          GroupId -> (string)

            

            The ID of the security group.

            

            

          

        

      AddressingType -> (string)

        

        Deprecated.

        

        

      BlockDeviceMappings -> (list)

        

        One or more block device mapping entries.

         

        Although you can specify encrypted EBS volumes in this block device mapping for your Spot Instances, these volumes are not encrypted.

        

        (structure)

          

          Describes a block device mapping.

          

          DeviceName -> (string)

            

            The device name exposed to the instance (for example, ``/dev/sdh`` or ``xvdh`` ).

            

            

          VirtualName -> (string)

            

            The virtual device name (``ephemeral`` N). Instance store volumes are numbered starting from 0. An instance type with 2 available instance store volumes can specify mappings for ``ephemeral0`` and ``ephemeral1`` .The number of available instance store volumes depends on the instance type. After you connect to the instance, you must mount the volume.

             

            Constraints: For M3 instances, you must specify instance store volumes in the block device mapping for the instance. When you launch an M3 instance, we ignore any instance store volumes specified in the block device mapping for the AMI.

            

            

          Ebs -> (structure)

            

            Parameters used to automatically set up EBS volumes when the instance is launched.

            

            Encrypted -> (boolean)

              

              Indicates whether the EBS volume is encrypted. Encrypted Amazon EBS volumes may only be attached to instances that support Amazon EBS encryption.

              

              

            DeleteOnTermination -> (boolean)

              

              Indicates whether the EBS volume is deleted on instance termination.

              

              

            Iops -> (integer)

              

              The number of I/O operations per second (IOPS) that the volume supports. For ``io1`` , this represents the number of IOPS that are provisioned for the volume. For ``gp2`` , this represents the baseline performance of the volume and the rate at which the volume accumulates I/O credits for bursting. For more information about General Purpose SSD baseline performance, I/O credits, and bursting, see `Amazon EBS Volume Types <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

               

              Constraint: Range is 100-20000 IOPS for ``io1`` volumes and 100-10000 IOPS for ``gp2`` volumes.

               

              Condition: This parameter is required for requests to create ``io1`` volumes; it is not used in requests to create ``gp2`` , ``st1`` , ``sc1`` , or ``standard`` volumes.

              

              

            SnapshotId -> (string)

              

              The ID of the snapshot.

              

              

            VolumeSize -> (integer)

              

              The size of the volume, in GiB.

               

              Constraints: 1-16384 for General Purpose SSD (``gp2`` ), 4-16384 for Provisioned IOPS SSD (``io1`` ), 500-16384 for Throughput Optimized HDD (``st1`` ), 500-16384 for Cold HDD (``sc1`` ), and 1-1024 for Magnetic (``standard`` ) volumes. If you specify a snapshot, the volume size must be equal to or larger than the snapshot size.

               

              Default: If you're creating the volume from a snapshot and don't specify a volume size, the default is the snapshot size.

              

              

            VolumeType -> (string)

              

              The volume type: ``gp2`` , ``io1`` , ``st1`` , ``sc1`` , or ``standard`` .

               

              Default: ``standard``  

              

              

            

          NoDevice -> (string)

            

            Suppresses the specified device included in the block device mapping of the AMI.

            

            

          

        

      EbsOptimized -> (boolean)

        

        Indicates whether the instance is optimized for EBS I/O. This optimization provides dedicated throughput to Amazon EBS and an optimized configuration stack to provide optimal EBS I/O performance. This optimization isn't available with all instance types. Additional usage charges apply when using an EBS Optimized instance.

         

        Default: ``false``  

        

        

      IamInstanceProfile -> (structure)

        

        The IAM instance profile.

        

        Arn -> (string)

          

          The Amazon Resource Name (ARN) of the instance profile.

          

          

        Name -> (string)

          

          The name of the instance profile.

          

          

        

      ImageId -> (string)

        

        The ID of the AMI.

        

        

      InstanceType -> (string)

        

        The instance type.

        

        

      KernelId -> (string)

        

        The ID of the kernel.

        

        

      KeyName -> (string)

        

        The name of the key pair.

        

        

      NetworkInterfaces -> (list)

        

        One or more network interfaces. If you specify a network interface, you must specify subnet IDs and security group IDs using the network interface.

        

        (structure)

          

          Describes a network interface.

          

          AssociatePublicIpAddress -> (boolean)

            

            Indicates whether to assign a public IPv4 address to an instance you launch in a VPC. The public IP address can only be assigned to a network interface for eth0, and can only be assigned to a new network interface, not an existing one. You cannot specify more than one network interface in the request. If launching into a default subnet, the default value is ``true`` .

            

            

          DeleteOnTermination -> (boolean)

            

            If set to ``true`` , the interface is deleted when the instance is terminated. You can specify ``true`` only if creating a new network interface when launching an instance.

            

            

          Description -> (string)

            

            The description of the network interface. Applies only if creating a network interface when launching an instance.

            

            

          DeviceIndex -> (integer)

            

            The index of the device on the instance for the network interface attachment. If you are specifying a network interface in a  run-instances request, you must provide the device index.

            

            

          Groups -> (list)

            

            The IDs of the security groups for the network interface. Applies only if creating a network interface when launching an instance.

            

            (string)

              

              

            

          Ipv6AddressCount -> (integer)

            

            A number of IPv6 addresses to assign to the network interface. Amazon EC2 chooses the IPv6 addresses from the range of the subnet. You cannot specify this option and the option to assign specific IPv6 addresses in the same request. You can specify this option if you've specified a minimum number of instances to launch.

            

            

          Ipv6Addresses -> (list)

            

            One or more IPv6 addresses to assign to the network interface. You cannot specify this option and the option to assign a number of IPv6 addresses in the same request. You cannot specify this option if you've specified a minimum number of instances to launch.

            

            (structure)

              

              Describes an IPv6 address.

              

              Ipv6Address -> (string)

                

                The IPv6 address.

                

                

              

            

          NetworkInterfaceId -> (string)

            

            The ID of the network interface.

            

            

          PrivateIpAddress -> (string)

            

            The private IPv4 address of the network interface. Applies only if creating a network interface when launching an instance. You cannot specify this option if you're launching more than one instance in a  run-instances request.

            

            

          PrivateIpAddresses -> (list)

            

            One or more private IPv4 addresses to assign to the network interface. Only one private IPv4 address can be designated as primary. You cannot specify this option if you're launching more than one instance in a  run-instances request.

            

            (structure)

              

              Describes a secondary private IPv4 address for a network interface.

              

              Primary -> (boolean)

                

                Indicates whether the private IPv4 address is the primary private IPv4 address. Only one IPv4 address can be designated as primary.

                

                

              PrivateIpAddress -> (string)

                

                The private IPv4 addresses.

                

                

              

            

          SecondaryPrivateIpAddressCount -> (integer)

            

            The number of secondary private IPv4 addresses. You can't specify this option and specify more than one private IP address using the private IP addresses option. You cannot specify this option if you're launching more than one instance in a  run-instances request.

            

            

          SubnetId -> (string)

            

            The ID of the subnet associated with the network string. Applies only if creating a network interface when launching an instance.

            

            

          

        

      Placement -> (structure)

        

        The placement information for the instance.

        

        AvailabilityZone -> (string)

          

          The Availability Zone.

           

          [Spot fleet only] To specify multiple Availability Zones, separate them using commas; for example, "us-west-2a, us-west-2b".

          

          

        GroupName -> (string)

          

          The name of the placement group (for cluster instances).

          

          

        Tenancy -> (string)

          

          The tenancy of the instance (if the instance is running in a VPC). An instance with a tenancy of ``dedicated`` runs on single-tenant hardware. The ``host`` tenancy is not supported for Spot instances.

          

          

        

      RamdiskId -> (string)

        

        The ID of the RAM disk.

        

        

      SubnetId -> (string)

        

        The ID of the subnet in which to launch the instance.

        

        

      Monitoring -> (structure)

        

        Describes the monitoring of an instance.

        

        Enabled -> (boolean)

          

          Indicates whether detailed monitoring is enabled. Otherwise, basic monitoring is enabled.

          

          

        

      

    LaunchedAvailabilityZone -> (string)

      

      The Availability Zone in which the bid is launched.

      

      

    ProductDescription -> (string)

      

      The product description associated with the Spot instance.

      

      

    SpotInstanceRequestId -> (string)

      

      The ID of the Spot instance request.

      

      

    SpotPrice -> (string)

      

      The maximum hourly price (bid) for the Spot instance launched to fulfill the request.

      

      

    State -> (string)

      

      The state of the Spot instance request. Spot bid status information can help you track your Spot instance requests. For more information, see `Spot Bid Status <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-bid-status.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

      

      

    Status -> (structure)

      

      The status code and status message describing the Spot instance request.

      

      Code -> (string)

        

        The status code. For a list of status codes, see `Spot Bid Status Codes <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-bid-status.html#spot-instance-bid-status-understand>`_ in the *Amazon Elastic Compute Cloud User Guide* .

        

        

      Message -> (string)

        

        The description for the status code.

        

        

      UpdateTime -> (timestamp)

        

        The date and time of the most recent status update, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z).

        

        

      

    Tags -> (list)

      

      Any tags assigned to the resource.

      

      (structure)

        

        Describes a tag.

        

        Key -> (string)

          

          The key of the tag.

           

          Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:``  

          

          

        Value -> (string)

          

          The value of the tag.

           

          Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

          

          

        

      

    Type -> (string)

      

      The Spot instance request type.

      

      

    ValidFrom -> (timestamp)

      

      The start date of the request, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z). The request becomes active at this date and time.

      

      

    ValidUntil -> (timestamp)

      

      The end date of the request, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z). If this is a one-time request, it remains active until all instances launch, the request is canceled, or this date is reached. If the request is persistent, it remains active until it is canceled or this date is reached.

      

      

    

  

