[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-spot-instance-requests:


*******************************
describe-spot-instance-requests
*******************************



===========
Description
===========



Describes the Spot instance requests that belong to your account. Spot instances are instances that Amazon EC2 launches when the bid price that you specify exceeds the current Spot price. Amazon EC2 periodically sets the Spot price based on available Spot instance capacity and current Spot instance requests. For more information, see `Spot Instance Requests <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-requests.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

You can use ``describe-spot-instance-requests`` to find a running Spot instance by examining the response. If the status of the Spot instance is ``fulfilled`` , the instance ID appears in the response and contains the identifier of the instance. Alternatively, you can use  describe-instances with a filter to look for instances where the instance lifecycle is ``spot`` .

 

Spot instance requests are deleted 4 hours after they are canceled and their instances are terminated.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeSpotInstanceRequests>`_


========
Synopsis
========

::

    describe-spot-instance-requests
  [--filters <value>]
  [--dry-run | --no-dry-run]
  [--spot-instance-request-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``availability-zone-group`` - The Availability Zone group. 
   
  * ``create-time`` - The time stamp when the Spot instance request was created. 
   
  * ``fault-code`` - The fault code related to the request. 
   
  * ``fault-message`` - The fault message related to the request. 
   
  * ``instance-id`` - The ID of the instance that fulfilled the request. 
   
  * ``launch-group`` - The Spot instance launch group. 
   
  * ``launch.block-device-mapping.delete-on-termination`` - Indicates whether the Amazon EBS volume is deleted on instance termination. 
   
  * ``launch.block-device-mapping.device-name`` - The device name for the Amazon EBS volume (for example, ``/dev/sdh`` ). 
   
  * ``launch.block-device-mapping.snapshot-id`` - The ID of the snapshot used for the Amazon EBS volume. 
   
  * ``launch.block-device-mapping.volume-size`` - The size of the Amazon EBS volume, in GiB. 
   
  * ``launch.block-device-mapping.volume-type`` - The type of the Amazon EBS volume: ``gp2`` for General Purpose SSD, ``io1`` for Provisioned IOPS SSD, ``st1`` for Throughput Optimized HDD, ``sc1`` for Cold HDD, or ``standard`` for Magnetic. 
   
  * ``launch.group-id`` - The security group for the instance. 
   
  * ``launch.image-id`` - The ID of the AMI. 
   
  * ``launch.instance-type`` - The type of instance (for example, ``m3.medium`` ). 
   
  * ``launch.kernel-id`` - The kernel ID. 
   
  * ``launch.key-name`` - The name of the key pair the instance launched with. 
   
  * ``launch.monitoring-enabled`` - Whether monitoring is enabled for the Spot instance. 
   
  * ``launch.ramdisk-id`` - The RAM disk ID. 
   
  * ``network-interface.network-interface-id`` - The ID of the network interface. 
   
  * ``network-interface.device-index`` - The index of the device for the network interface attachment on the instance. 
   
  * ``network-interface.subnet-id`` - The ID of the subnet for the instance. 
   
  * ``network-interface.description`` - A description of the network interface. 
   
  * ``network-interface.private-ip-address`` - The primary private IP address of the network interface. 
   
  * ``network-interface.delete-on-termination`` - Indicates whether the network interface is deleted when the instance is terminated. 
   
  * ``network-interface.group-id`` - The ID of the security group associated with the network interface. 
   
  * ``network-interface.group-name`` - The name of the security group associated with the network interface. 
   
  * ``network-interface.addresses.primary`` - Indicates whether the IP address is the primary private IP address. 
   
  * ``product-description`` - The product description associated with the instance (``Linux/UNIX`` | ``Windows`` ). 
   
  * ``spot-instance-request-id`` - The Spot instance request ID. 
   
  * ``spot-price`` - The maximum hourly price for any Spot instance launched to fulfill the request. 
   
  * ``state`` - The state of the Spot instance request (``open`` | ``active`` | ``closed`` | ``cancelled`` | ``failed`` ). Spot bid status information can help you track your Amazon EC2 Spot instance requests. For more information, see `Spot Bid Status <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-bid-status.html>`_ in the Amazon Elastic Compute Cloud User Guide. 
   
  * ``status-code`` - The short code describing the most recent evaluation of your Spot instance request. 
   
  * ``status-message`` - The message explaining the status of the Spot instance request. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. Specify the key of the tag in the filter name and the value of the tag in the filter value. For example, for the tag Purpose=X, specify ``tag:Purpose`` for the filter name and ``X`` for the filter value. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``type`` - The type of Spot instance request (``one-time`` | ``persistent`` ). 
   
  * ``launched-availability-zone`` - The Availability Zone in which the bid is launched. 
   
  * ``valid-from`` - The start date of the request. 
   
  * ``valid-until`` - The end date of the request. 
   

  



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



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--spot-instance-request-ids`` (list)


  One or more Spot instance request IDs.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe Spot Instance requests**

This example describes all of your Spot Instance requests.

Command::

  aws ec2 describe-spot-instance-requests

Output::

  {
    "SpotInstanceRequests": [
      {
        "Status": {
          "UpdateTime": "2014-04-30T18:16:21.000Z",
          "Code": "fulfilled",
          "Message": "Your Spot request is fulfilled."
        },
        "ProductDescription": "Linux/UNIX",
        "InstanceId": "i-1234567890abcdef0",
        "SpotInstanceRequestId": "sir-08b93456",
        "State": "active",
        "LaunchedAvailabilityZone": "us-west-1b",
        "LaunchSpecification": {
          "ImageId": "ami-7aba833f",
          "KeyName": "May14Key",
          "BlockDeviceMappings": [
            {
              "DeviceName": "/dev/sda1",
              "Ebs": {
                "DeleteOnTermination": true,
                "VolumeType": "standard",
                "VolumeSize": 8
              }
            }
          ],
          "EbsOptimized": false,
          "SecurityGroups": [
            {
              "GroupName": "launch-wizard-1",
              "GroupId": "sg-e38f24a7"
            }
          ],
          "InstanceType": "m1.small"
        },
        "Type": "one-time",
        "CreateTime": "2014-04-30T18:14:55.000Z",
        "SpotPrice": "0.010000"
      },
      {
        "Status": {
          "UpdateTime": "2014-04-30T18:16:21.000Z",
          "Code": "fulfilled",
          "Message": "Your Spot request is fulfilled."
        },
        "ProductDescription": "Linux/UNIX",
        "InstanceId": "i-1234567890abcdef1",
        "SpotInstanceRequestId": "sir-285b1e56",
        "State": "active",
        "LaunchedAvailabilityZone": "us-west-1b",
        "LaunchSpecification": {
          "ImageId": "ami-7aba833f",
          "KeyName": "May14Key",
          "BlockDeviceMappings": [
            {
              "DeviceName": "/dev/sda1",
              "Ebs": {
                "DeleteOnTermination": true,
                "VolumeType": "standard",
                "VolumeSize": 8
              }
            }
          ],
          "EbsOptimized": false,
          "SecurityGroups": [
            {
              "GroupName": "launch-wizard-1",
              "GroupId": "sg-e38f24a7"
            }
          ],
          "InstanceType": "m1.small"
        },
        "Type": "one-time",
        "CreateTime": "2014-04-30T18:14:55.000Z",
        "SpotPrice": "0.010000"
      }
    ]
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

      

      

    

  

