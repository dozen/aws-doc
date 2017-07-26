[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-spot-instance-requests:


*******************************
describe-spot-instance-requests
*******************************



===========
Description
===========



Describes the Spot instance requests that belong to your account. Spot instances are instances that Amazon EC2 launches when the bid price that you specify exceeds the current Spot price. Amazon EC2 periodically sets the Spot price based on available Spot instance capacity and current Spot instance requests. For more information, see `Spot Instance Requests`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

You can use ``describe-spot-instance-requests`` to find a running Spot instance by examining the response. If the status of the Spot instance is ``fulfilled`` , the instance ID appears in the response and contains the identifier of the instance. Alternatively, you can use  describe-instances with a filter to look for instances where the instance lifecycle is ``spot`` .



========
Synopsis
========

::

    describe-spot-instance-requests
  [--dry-run | --no-dry-run]
  [--spot-instance-request-ids <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--spot-instance-request-ids`` (list)


  One or more Spot instance request IDs.

  



Syntax::

  "string" "string" ...



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
   
  * ``launch.block-device-mapping.volume-type`` - The type of the Amazon EBS volume (``gp2`` | ``standard`` | ``io1`` ). 
   
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
   
  * ``state`` - The state of the Spot instance request (``open`` | ``active`` | ``closed`` | ``cancelled`` | ``failed`` ). Spot bid status information can help you track your Amazon EC2 Spot instance requests. For more information, see `Spot Bid Status`_ in the Amazon Elastic Compute Cloud User Guide. 
   
  * ``status-code`` - The short code describing the most recent evaluation of your Spot instance request. 
   
  * ``status-message`` - The message explaining the status of the Spot instance request. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. 
   
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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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
        "InstanceId": "i-20170a7c",
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
        "InstanceId": "i-894f53d5",
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

    

    SpotInstanceRequestId -> (string)

      

      The ID of the Spot instance request.

      

      

    SpotPrice -> (string)

      

      The maximum hourly price (bid) for the Spot instance launched to fulfill the request.

      

      

    Type -> (string)

      

      The Spot instance request type.

      

      

    State -> (string)

      

      The state of the Spot instance request. Spot bid status information can help you track your Spot instance requests. For more information, see `Spot Bid Status`_ in the *Amazon Elastic Compute Cloud User Guide* .

      

      

    Fault -> (structure)

      

      The fault codes for the Spot instance request, if any.

      

      Code -> (string)

        

        The reason code for the Spot instance state change.

        

        

      Message -> (string)

        

        The message for the Spot instance state change.

        

        

      

    Status -> (structure)

      

      The status code and status message describing the Spot instance request.

      

      Code -> (string)

        

        The status code. For a list of status codes, see `Spot Bid Status Codes`_ in the *Amazon Elastic Compute Cloud User Guide* .

        

        

      UpdateTime -> (timestamp)

        

        The date and time of the most recent status update, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z).

        

        

      Message -> (string)

        

        The description for the status code.

        

        

      

    ValidFrom -> (timestamp)

      

      The start date of the request, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z). The request becomes active at this date and time.

      

      

    ValidUntil -> (timestamp)

      

      The end date of the request, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z). If this is a one-time request, it remains active until all instances launch, the request is canceled, or this date is reached. If the request is persistent, it remains active until it is canceled or this date is reached.

      

      

    LaunchGroup -> (string)

      

      The instance launch group. Launch groups are Spot instances that launch together and terminate together.

      

      

    AvailabilityZoneGroup -> (string)

      

      The Availability Zone group. If you specify the same Availability Zone group for all Spot instance requests, all Spot instances are launched in the same Availability Zone.

      

      

    LaunchSpecification -> (structure)

      

      Additional information for launching instances.

      

      ImageId -> (string)

        

        The ID of the AMI.

        

        

      KeyName -> (string)

        

        The name of the key pair.

        

        

      SecurityGroups -> (list)

        

        One or more security groups. When requesting instances in a VPC, you must specify the IDs of the security groups. When requesting instances in EC2-Classic, you can specify the names or the IDs of the security groups.

        

        (structure)

          

          Describes a security group.

          

          GroupName -> (string)

            

            The name of the security group.

            

            

          GroupId -> (string)

            

            The ID of the security group.

            

            

          

        

      UserData -> (string)

        

        The Base64-encoded MIME user data to make available to the instances.

        

        

      AddressingType -> (string)

        

        Deprecated.

        

        

      InstanceType -> (string)

        

        The instance type.

        

        

      Placement -> (structure)

        

        The placement information for the instance.

        

        AvailabilityZone -> (string)

          

          The Availability Zones. To specify multiple Availability Zones, separate them using commas; for example, "us-west-2a, us-west-2b".

          

          

        GroupName -> (string)

          

          The name of the placement group (for cluster instances).

          

          

        

      KernelId -> (string)

        

        The ID of the kernel.

        

        

      RamdiskId -> (string)

        

        The ID of the RAM disk.

        

        

      BlockDeviceMappings -> (list)

        

        One or more block device mapping entries.

        

        (structure)

          

          Describes a block device mapping.

          

          VirtualName -> (string)

            

            The virtual device name (``ephemeral`` N). Instance store volumes are numbered starting from 0. An instance type with 2 available instance store volumes can specify mappings for ``ephemeral0`` and ``ephemeral1`` .The number of available instance store volumes depends on the instance type. After you connect to the instance, you must mount the volume.

             

            Constraints: For M3 instances, you must specify instance store volumes in the block device mapping for the instance. When you launch an M3 instance, we ignore any instance store volumes specified in the block device mapping for the AMI.

            

            

          DeviceName -> (string)

            

            The device name exposed to the instance (for example, ``/dev/sdh`` or ``xvdh`` ).

            

            

          Ebs -> (structure)

            

            Parameters used to automatically set up EBS volumes when the instance is launched.

            

            SnapshotId -> (string)

              

              The ID of the snapshot.

              

              

            VolumeSize -> (integer)

              

              The size of the volume, in GiB.

               

              Constraints: ``1-1024`` for ``standard`` volumes, ``1-16384`` for ``gp2`` volumes, and ``4-16384`` for ``io1`` volumes. If you specify a snapshot, the volume size must be equal to or larger than the snapshot size.

               

              Default: If you're creating the volume from a snapshot and don't specify a volume size, the default is the snapshot size.

              

              

            DeleteOnTermination -> (boolean)

              

              Indicates whether the EBS volume is deleted on instance termination.

              

              

            VolumeType -> (string)

              

              The volume type. ``gp2`` for General Purpose (SSD) volumes, ``io1`` for Provisioned IOPS (SSD) volumes, and ``standard`` for Magnetic volumes.

               

              Default: ``standard`` 

              

              

            Iops -> (integer)

              

              The number of I/O operations per second (IOPS) that the volume supports. For Provisioned IOPS (SSD) volumes, this represents the number of IOPS that are provisioned for the volume. For General Purpose (SSD) volumes, this represents the baseline performance of the volume and the rate at which the volume accumulates I/O credits for bursting. For more information on General Purpose (SSD) baseline performance, I/O credits, and bursting, see `Amazon EBS Volume Types`_ in the *Amazon Elastic Compute Cloud User Guide* .

               

              Constraint: Range is 100 to 20000 for Provisioned IOPS (SSD) volumes and 3 to 10000 for General Purpose (SSD) volumes.

               

              Condition: This parameter is required for requests to create ``io1`` volumes; it is not used in requests to create ``standard`` or ``gp2`` volumes.

              

              

            Encrypted -> (boolean)

              

              Indicates whether the EBS volume is encrypted. Encrypted Amazon EBS volumes may only be attached to instances that support Amazon EBS encryption.

              

              

            

          NoDevice -> (string)

            

            Suppresses the specified device included in the block device mapping of the AMI.

            

            

          

        

      SubnetId -> (string)

        

        The ID of the subnet in which to launch the instance.

        

        

      NetworkInterfaces -> (list)

        

        One or more network interfaces.

        

        (structure)

          

          Describes a network interface.

          

          NetworkInterfaceId -> (string)

            

            The ID of the network interface.

            

            

          DeviceIndex -> (integer)

            

            The index of the device on the instance for the network interface attachment. If you are specifying a network interface in a  run-instances request, you must provide the device index.

            

            

          SubnetId -> (string)

            

            The ID of the subnet associated with the network string. Applies only if creating a network interface when launching an instance.

            

            

          Description -> (string)

            

            The description of the network interface. Applies only if creating a network interface when launching an instance.

            

            

          PrivateIpAddress -> (string)

            

            The private IP address of the network interface. Applies only if creating a network interface when launching an instance.

            

            

          Groups -> (list)

            

            The IDs of the security groups for the network interface. Applies only if creating a network interface when launching an instance.

            

            (string)

              

              

            

          DeleteOnTermination -> (boolean)

            

            If set to ``true`` , the interface is deleted when the instance is terminated. You can specify ``true`` only if creating a new network interface when launching an instance.

            

            

          PrivateIpAddresses -> (list)

            

            One or more private IP addresses to assign to the network interface. Only one private IP address can be designated as primary.

            

            (structure)

              

              Describes a secondary private IP address for a network interface.

              

              PrivateIpAddress -> (string)

                

                The private IP addresses.

                

                

              Primary -> (boolean)

                

                Indicates whether the private IP address is the primary private IP address. Only one IP address can be designated as primary.

                

                

              

            

          SecondaryPrivateIpAddressCount -> (integer)

            

            The number of secondary private IP addresses. You can't specify this option and specify more than one private IP address using the private IP addresses option.

            

            

          AssociatePublicIpAddress -> (boolean)

            

            Indicates whether to assign a public IP address to an instance you launch in a VPC. The public IP address can only be assigned to a network interface for eth0, and can only be assigned to a new network interface, not an existing one. You cannot specify more than one network interface in the request. If launching into a default subnet, the default value is ``true`` .

            

            

          

        

      IamInstanceProfile -> (structure)

        

        The IAM instance profile.

        

        Arn -> (string)

          

          The Amazon Resource Name (ARN) of the instance profile.

          

          

        Name -> (string)

          

          The name of the instance profile.

          

          

        

      EbsOptimized -> (boolean)

        

        Indicates whether the instance is optimized for EBS I/O. This optimization provides dedicated throughput to Amazon EBS and an optimized configuration stack to provide optimal EBS I/O performance. This optimization isn't available with all instance types. Additional usage charges apply when using an EBS Optimized instance.

         

        Default: ``false`` 

        

        

      Monitoring -> (structure)

        

        Describes the monitoring for the instance.

        

        Enabled -> (boolean)

          

          Indicates whether monitoring is enabled for the instance.

          

          

        

      

    InstanceId -> (string)

      

      The instance ID, if an instance has been launched to fulfill the Spot instance request.

      

      

    CreateTime -> (timestamp)

      

      The date and time when the Spot instance request was created, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z).

      

      

    ProductDescription -> (string)

      

      The product description associated with the Spot instance.

      

      

    BlockDurationMinutes -> (integer)

      

      The duration for the Spot instance, in minutes.

      

      

    ActualBlockHourlyPrice -> (string)

      

      If you specified a duration and your Spot instance request was fulfilled, this is the fixed hourly price in effect for the Spot instance while it runs.

      

      

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

          

          

        

      

    LaunchedAvailabilityZone -> (string)

      

      The Availability Zone in which the bid is launched.

      

      

    

  



.. _Amazon EBS Volume Types: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html
.. _Spot Instance Requests: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-requests.html
.. _Spot Bid Status Codes: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-bid-status.html#spot-instance-bid-status-understand
.. _Spot Bid Status: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-bid-status.html
