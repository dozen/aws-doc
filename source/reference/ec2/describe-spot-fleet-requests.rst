[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-spot-fleet-requests:


****************************
describe-spot-fleet-requests
****************************



===========
Description
===========



Describes your Spot fleet requests.

 

Spot fleet requests are deleted 48 hours after they are canceled and their instances are terminated.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeSpotFleetRequests>`_


``describe-spot-fleet-requests`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``SpotFleetRequestConfigs``


========
Synopsis
========

::

    describe-spot-fleet-requests
  [--dry-run | --no-dry-run]
  [--spot-fleet-request-ids <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--spot-fleet-request-ids`` (list)


  The IDs of the Spot fleet requests.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe your Spot fleet requests**

This example describes all of your Spot fleet requests.

Command::

  aws ec2 describe-spot-fleet-requests

Output::

  {
    "SpotFleetRequestConfigs": [
        {
            "SpotFleetRequestId": "sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE",
            "SpotFleetRequestConfig": {
                "TargetCapacity": 20,
                "LaunchSpecifications": [
                    {
                        "EbsOptimized": false,
                        "NetworkInterfaces": [
                            {
                                "SubnetId": "subnet-a61dafcf",
                                "DeviceIndex": 0,
                                "DeleteOnTermination": false,
                                "AssociatePublicIpAddress": true,
                                "SecondaryPrivateIpAddressCount": 0
                            }
                        ],
                        "InstanceType": "cc2.8xlarge",
                        "ImageId": "ami-1a2b3c4d"
                    },
                    {
                        "EbsOptimized": false,
                        "NetworkInterfaces": [
                            {
                                "SubnetId": "subnet-a61dafcf",
                                "DeviceIndex": 0,
                                "DeleteOnTermination": false,
                                "AssociatePublicIpAddress": true,
                                "SecondaryPrivateIpAddressCount": 0
                            }
                        ],
                        "InstanceType": "r3.8xlarge",
                        "ImageId": "ami-1a2b3c4d"
                    }
                ],
                "SpotPrice": "0.05",
                "IamFleetRole": "arn:aws:iam::123456789012:role/my-spot-fleet-role"
            },
            "SpotFleetRequestState": "active"
        },  
        {
            "SpotFleetRequestId": "sfr-306341ed-9739-402e-881b-ce47bEXAMPLE",
            "SpotFleetRequestConfig": {
                "TargetCapacity": 20,
                "LaunchSpecifications": [
                    {
                        "EbsOptimized": false,
                        "NetworkInterfaces": [
                            {
                                "SubnetId": "subnet-6e7f829e",
                                "DeviceIndex": 0,
                                "DeleteOnTermination": false,
                                "AssociatePublicIpAddress": true,
                                "SecondaryPrivateIpAddressCount": 0
                            }
                        ],
                        "InstanceType": "m3.medium",
                        "ImageId": "ami-1a2b3c4d"
                    }
                ],
                "SpotPrice": "0.05",
                "IamFleetRole": "arn:aws:iam::123456789012:role/my-spot-fleet-role"
            },
            "SpotFleetRequestState": "active"
        }
    ]
  }

**To describe a Spot fleet request**

This example describes the specified Spot fleet request.

Command::

  aws ec2 describe-spot-fleet-requests --spot-fleet-request-ids sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE

Output::

  {
    "SpotFleetRequestConfigs": [
        {
            "SpotFleetRequestId": "sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE",
            "SpotFleetRequestConfig": {
                "TargetCapacity": 20,
                "LaunchSpecifications": [
                    {
                        "EbsOptimized": false,
                        "NetworkInterfaces": [
                            {
                                "SubnetId": "subnet-a61dafcf",
                                "DeviceIndex": 0,
                                "DeleteOnTermination": false,
                                "AssociatePublicIpAddress": true,
                                "SecondaryPrivateIpAddressCount": 0
                            }
                        ],
                        "InstanceType": "cc2.8xlarge",
                        "ImageId": "ami-1a2b3c4d"
                    },
                    {
                        "EbsOptimized": false,
                        "NetworkInterfaces": [
                            {
                                "SubnetId": "subnet-a61dafcf",
                                "DeviceIndex": 0,
                                "DeleteOnTermination": false,
                                "AssociatePublicIpAddress": true,
                                "SecondaryPrivateIpAddressCount": 0
                            }
                        ],
                        "InstanceType": "r3.8xlarge",
                        "ImageId": "ami-1a2b3c4d"
                    }
                ],
                "SpotPrice": "0.05",
                "IamFleetRole": "arn:aws:iam::123456789012:role/my-spot-fleet-role"
            },
            "SpotFleetRequestState": "active"
        }
    ]
  }


======
Output
======

NextToken -> (string)

  

  The token required to retrieve the next set of results. This value is ``null`` when there are no more results to return.

  

  

SpotFleetRequestConfigs -> (list)

  

  Information about the configuration of your Spot fleet.

  

  (structure)

    

    Describes a Spot fleet request.

    

    ActivityStatus -> (string)

      

      The progress of the Spot fleet request. If there is an error, the status is ``error`` . After all bids are placed, the status is ``pending_fulfillment`` . If the size of the fleet is equal to or greater than its target capacity, the status is ``fulfilled`` . If the size of the fleet is decreased, the status is ``pending_termination`` while Spot instances are terminating.

      

      

    CreateTime -> (timestamp)

      

      The creation date and time of the request.

      

      

    SpotFleetRequestConfig -> (structure)

      

      Information about the configuration of the Spot fleet request.

      

      AllocationStrategy -> (string)

        

        Indicates how to allocate the target capacity across the Spot pools specified by the Spot fleet request. The default is ``lowestPrice`` .

        

        

      ClientToken -> (string)

        

        A unique, case-sensitive identifier you provide to ensure idempotency of your listings. This helps avoid duplicate listings. For more information, see `Ensuring Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/Run_Instance_Idempotency.html>`_ .

        

        

      ExcessCapacityTerminationPolicy -> (string)

        

        Indicates whether running Spot instances should be terminated if the target capacity of the Spot fleet request is decreased below the current size of the Spot fleet.

        

        

      FulfilledCapacity -> (double)

        

        The number of units fulfilled by this request compared to the set target capacity.

        

        

      IamFleetRole -> (string)

        

        Grants the Spot fleet permission to terminate Spot instances on your behalf when you cancel its Spot fleet request using  cancel-spot-fleet-requests or when the Spot fleet request expires, if you set ``terminateInstancesWithExpiration`` .

        

        

      LaunchSpecifications -> (list)

        

        Information about the launch specifications for the Spot fleet request.

        

        (structure)

          

          Describes the launch specification for one or more Spot instances.

          

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

            

            Indicates whether the instances are optimized for EBS I/O. This optimization provides dedicated throughput to Amazon EBS and an optimized configuration stack to provide optimal EBS I/O performance. This optimization isn't available with all instance types. Additional usage charges apply when using an EBS Optimized instance.

             

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

            

            The instance type. Note that T2 and HS1 instance types are not supported.

            

            

          KernelId -> (string)

            

            The ID of the kernel.

            

            

          KeyName -> (string)

            

            The name of the key pair.

            

            

          Monitoring -> (structure)

            

            Enable or disable monitoring for the instances.

            

            Enabled -> (boolean)

              

              Enables monitoring for the instance.

               

              Default: ``false``  

              

              

            

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

            

            The placement information.

            

            AvailabilityZone -> (string)

              

              The Availability Zone.

               

              [Spot fleet only] To specify multiple Availability Zones, separate them using commas; for example, "us-west-2a, us-west-2b".

              

              

            GroupName -> (string)

              

              The name of the placement group (for cluster instances).

              

              

            Tenancy -> (string)

              

              The tenancy of the instance (if the instance is running in a VPC). An instance with a tenancy of ``dedicated`` runs on single-tenant hardware. The ``host`` tenancy is not supported for Spot instances.

              

              

            

          RamdiskId -> (string)

            

            The ID of the RAM disk.

            

            

          SpotPrice -> (string)

            

            The bid price per unit hour for the specified instance type. If this value is not specified, the default is the Spot bid price specified for the fleet. To determine the bid price per unit hour, divide the Spot bid price by the value of ``WeightedCapacity`` .

            

            

          SubnetId -> (string)

            

            The ID of the subnet in which to launch the instances. To specify multiple subnets, separate them using commas; for example, "subnet-a61dafcf, subnet-65ea5f08".

            

            

          UserData -> (string)

            

            The user data to make available to the instances. If you are using an AWS SDK or command line tool, Base64-encoding is performed for you, and you can load the text from a file. Otherwise, you must provide Base64-encoded text.

            

            

          WeightedCapacity -> (double)

            

            The number of units provided by the specified instance type. These are the same units that you chose to set the target capacity in terms (instances or a performance characteristic such as vCPUs, memory, or I/O).

             

            If the target capacity divided by this value is not a whole number, we round the number of instances to the next whole number. If this value is not specified, the default is 1.

            

            

          TagSpecifications -> (list)

            

            The tags to apply during creation.

            

            (structure)

              

              The tags for a Spot fleet resource.

              

              ResourceType -> (string)

                

                The type of resource. Currently, the only resource type that is supported is ``instance`` .

                

                

              Tags -> (list)

                

                The tags.

                

                (structure)

                  

                  Describes a tag.

                  

                  Key -> (string)

                    

                    The key of the tag.

                     

                    Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:``  

                    

                    

                  Value -> (string)

                    

                    The value of the tag.

                     

                    Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

                    

                    

                  

                

              

            

          

        

      SpotPrice -> (string)

        

        The bid price per unit hour.

        

        

      TargetCapacity -> (integer)

        

        The number of units to request. You can choose to set the target capacity in terms of instances or a performance characteristic that is important to your application workload, such as vCPUs, memory, or I/O.

        

        

      TerminateInstancesWithExpiration -> (boolean)

        

        Indicates whether running Spot instances should be terminated when the Spot fleet request expires.

        

        

      Type -> (string)

        

        The type of request. Indicates whether the fleet will only ``request`` the target capacity or also attempt to ``maintain`` it. When you ``request`` a certain target capacity, the fleet will only place the required bids. It will not attempt to replenish Spot instances if capacity is diminished, nor will it submit bids in alternative Spot pools if capacity is not available. When you want to ``maintain`` a certain target capacity, fleet will place the required bids to meet this target capacity. It will also automatically replenish any interrupted instances. Default: ``maintain`` .

        

        

      ValidFrom -> (timestamp)

        

        The start date and time of the request, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z). The default is to start fulfilling the request immediately.

        

        

      ValidUntil -> (timestamp)

        

        The end date and time of the request, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z). At this point, no new Spot instance requests are placed or enabled to fulfill the request.

        

        

      ReplaceUnhealthyInstances -> (boolean)

        

        Indicates whether Spot fleet should replace unhealthy instances.

        

        

      

    SpotFleetRequestId -> (string)

      

      The ID of the Spot fleet request.

      

      

    SpotFleetRequestState -> (string)

      

      The state of the Spot fleet request.

      

      

    

  

