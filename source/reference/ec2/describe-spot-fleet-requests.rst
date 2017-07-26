[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-spot-fleet-requests:


****************************
describe-spot-fleet-requests
****************************



===========
Description
===========



Describes your Spot fleet requests.



========
Synopsis
========

::

    describe-spot-fleet-requests
  [--dry-run | --no-dry-run]
  [--spot-fleet-request-ids <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--spot-fleet-request-ids`` (list)


  The IDs of the Spot fleet requests.

  



Syntax::

  "string" "string" ...



``--next-token`` (string)


  The token for the next set of results.

  

``--max-results`` (integer)


  The maximum number of results to return in a single call. Specify a value between 1 and 1000. The default value is 1000. To retrieve the remaining results, make another call with the returned ``NextToken`` value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

SpotFleetRequestConfigs -> (list)

  

  Information about the configuration of your Spot fleet.

  

  (structure)

    

    Describes a Spot fleet request.

    

    SpotFleetRequestId -> (string)

      

      The ID of the Spot fleet request.

      

      

    SpotFleetRequestState -> (string)

      

      The state of the Spot fleet request.

      

      

    SpotFleetRequestConfig -> (structure)

      

      Information about the configuration of the Spot fleet request.

      

      ClientToken -> (string)

        

        A unique, case-sensitive identifier you provide to ensure idempotency of your listings. This helps avoid duplicate listings. For more information, see `Ensuring Idempotency`_ .

        

        

      SpotPrice -> (string)

        

        The bid price per unit hour.

        

        

      TargetCapacity -> (integer)

        

        The number of units to request. You can choose to set the target capacity in terms of instances or a performance characteristic that is important to your application workload, such as vCPUs, memory, or I/O.

        

        

      ValidFrom -> (timestamp)

        

        The start date and time of the request, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z). The default is to start fulfilling the request immediately.

        

        

      ValidUntil -> (timestamp)

        

        The end date and time of the request, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z). At this point, no new Spot instance requests are placed or enabled to fulfill the request.

        

        

      TerminateInstancesWithExpiration -> (boolean)

        

        Indicates whether running Spot instances should be terminated when the Spot fleet request expires.

        

        

      IamFleetRole -> (string)

        

        Grants the Spot fleet permission to terminate Spot instances on your behalf when you cancel its Spot fleet request using  cancel-spot-fleet-requests or when the Spot fleet request expires, if you set ``terminateInstancesWithExpiration`` .

        

        

      LaunchSpecifications -> (list)

        

        Information about the launch specifications for the Spot fleet request.

        

        (structure)

          

          Describes the launch specification for one or more Spot instances.

          

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

            

            The placement information.

            

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

                

                

              

            

          Monitoring -> (structure)

            

            Enable or disable monitoring for the instances.

            

            Enabled -> (boolean)

              

              Enables monitoring for the instance.

               

              Default: ``false`` 

              

              

            

          SubnetId -> (string)

            

            The ID of the subnet in which to launch the instances. To specify multiple subnets, separate them using commas; for example, "subnet-a61dafcf, subnet-65ea5f08".

            

            

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

            

            Indicates whether the instances are optimized for EBS I/O. This optimization provides dedicated throughput to Amazon EBS and an optimized configuration stack to provide optimal EBS I/O performance. This optimization isn't available with all instance types. Additional usage charges apply when using an EBS Optimized instance.

             

            Default: ``false`` 

            

            

          WeightedCapacity -> (double)

            

            The number of units provided by the specified instance type. These are the same units that you chose to set the target capacity in terms (instances or a performance characteristic such as vCPUs, memory, or I/O).

             

            If the target capacity divided by this value is not a whole number, we round the number of instances to the next whole number. If this value is not specified, the default is 1.

            

            

          SpotPrice -> (string)

            

            The bid price per unit hour for the specified instance type. If this value is not specified, the default is the Spot bid price specified for the fleet. To determine the bid price per unit hour, divide the Spot bid price by the value of ``WeightedCapacity`` .

            

            

          

        

      ExcessCapacityTerminationPolicy -> (string)

        

        Indicates whether running Spot instances should be terminated if the target capacity of the Spot fleet request is decreased below the current size of the Spot fleet.

        

        

      AllocationStrategy -> (string)

        

        Indicates how to allocate the target capacity across the Spot pools specified by the Spot fleet request. The default is ``lowestPrice`` .

        

        

      

    CreateTime -> (timestamp)

      

      The creation date and time of the request.

      

      

    

  

NextToken -> (string)

  

  The token required to retrieve the next set of results. This value is ``null`` when there are no more results to return.

  

  



.. _Amazon EBS Volume Types: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html
.. _Ensuring Idempotency: http://docs.aws.amazon.com/AWSEC2/latest/APIReference/Run_Instance_Idempotency.html
