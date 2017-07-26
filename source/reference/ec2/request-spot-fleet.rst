[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 request-spot-fleet:


******************
request-spot-fleet
******************



===========
Description
===========



Creates a Spot fleet request.

 

You can submit a single request that includes multiple launch specifications that vary by instance type, AMI, Availability Zone, or subnet.

 

By default, the Spot fleet requests Spot instances in the Spot pool where the price per unit is the lowest. Each launch specification can include its own instance weighting that reflects the value of the instance type to your application workload.

 

Alternatively, you can specify that the Spot fleet distribute the target capacity across the Spot pools included in its launch specifications. By ensuring that the Spot instances in your Spot fleet are in different Spot pools, you can improve the availability of your fleet.

 

For more information, see `Spot Fleet Requests`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    request-spot-fleet
  [--dry-run | --no-dry-run]
  --spot-fleet-request-config <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--spot-fleet-request-config`` (structure)


  The configuration for the Spot fleet request.

  



JSON Syntax::

  {
    "ClientToken": "string",
    "SpotPrice": "string",
    "TargetCapacity": integer,
    "ValidFrom": timestamp,
    "ValidUntil": timestamp,
    "TerminateInstancesWithExpiration": true|false,
    "IamFleetRole": "string",
    "LaunchSpecifications": [
      {
        "ImageId": "string",
        "KeyName": "string",
        "SecurityGroups": [
          {
            "GroupName": "string",
            "GroupId": "string"
          }
          ...
        ],
        "UserData": "string",
        "AddressingType": "string",
        "InstanceType": "t1.micro"|"m1.small"|"m1.medium"|"m1.large"|"m1.xlarge"|"m3.medium"|"m3.large"|"m3.xlarge"|"m3.2xlarge"|"m4.large"|"m4.xlarge"|"m4.2xlarge"|"m4.4xlarge"|"m4.10xlarge"|"t2.nano"|"t2.micro"|"t2.small"|"t2.medium"|"t2.large"|"m2.xlarge"|"m2.2xlarge"|"m2.4xlarge"|"cr1.8xlarge"|"i2.xlarge"|"i2.2xlarge"|"i2.4xlarge"|"i2.8xlarge"|"hi1.4xlarge"|"hs1.8xlarge"|"c1.medium"|"c1.xlarge"|"c3.large"|"c3.xlarge"|"c3.2xlarge"|"c3.4xlarge"|"c3.8xlarge"|"c4.large"|"c4.xlarge"|"c4.2xlarge"|"c4.4xlarge"|"c4.8xlarge"|"cc1.4xlarge"|"cc2.8xlarge"|"g2.2xlarge"|"cg1.4xlarge"|"r3.large"|"r3.xlarge"|"r3.2xlarge"|"r3.4xlarge"|"r3.8xlarge"|"d2.xlarge"|"d2.2xlarge"|"d2.4xlarge"|"d2.8xlarge",
        "Placement": {
          "AvailabilityZone": "string",
          "GroupName": "string"
        },
        "KernelId": "string",
        "RamdiskId": "string",
        "BlockDeviceMappings": [
          {
            "VirtualName": "string",
            "DeviceName": "string",
            "Ebs": {
              "SnapshotId": "string",
              "VolumeSize": integer,
              "DeleteOnTermination": true|false,
              "VolumeType": "standard"|"io1"|"gp2",
              "Iops": integer,
              "Encrypted": true|false
            },
            "NoDevice": "string"
          }
          ...
        ],
        "Monitoring": {
          "Enabled": true|false
        },
        "SubnetId": "string",
        "NetworkInterfaces": [
          {
            "NetworkInterfaceId": "string",
            "DeviceIndex": integer,
            "SubnetId": "string",
            "Description": "string",
            "PrivateIpAddress": "string",
            "Groups": ["string", ...],
            "DeleteOnTermination": true|false,
            "PrivateIpAddresses": [
              {
                "PrivateIpAddress": "string",
                "Primary": true|false
              }
              ...
            ],
            "SecondaryPrivateIpAddressCount": integer,
            "AssociatePublicIpAddress": true|false
          }
          ...
        ],
        "IamInstanceProfile": {
          "Arn": "string",
          "Name": "string"
        },
        "EbsOptimized": true|false,
        "WeightedCapacity": double,
        "SpotPrice": "string"
      }
      ...
    ],
    "ExcessCapacityTerminationPolicy": "noTermination"|"default",
    "AllocationStrategy": "lowestPrice"|"diversified"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To request a Spot fleet in the subnet with the lowest price**

This example command creates a Spot fleet request with two launch specifications that differ only by subnet.
The Spot fleet launches the instances in the specified subnet with the lowest price.
If the instances are launched in a default VPC, they receive a public IP address by default.
If the instances are launched in a nondefault VPC, they do not receive a public IP address by default. 

Note that you can't specify different subnets from the same Availability Zone in a Spot fleet request.

Command::

  aws ec2 request-spot-fleet --spot-fleet-request-config file://config.json

Config.json:: 
  
  {
    "SpotPrice": "0.04",
    "TargetCapacity": 2,
    "IamFleetRole": "arn:aws:iam::123456789012:role/my-spot-fleet-role",
    "LaunchSpecifications": [
        {
            "ImageId": "ami-1a2b3c4d",
            "KeyName": "my-key-pair",
            "SecurityGroups": [
                {
                    "GroupId": "sg-1a2b3c4d"
                }
            ],
            "InstanceType": "m3.medium",
            "SubnetId": "subnet-1a2b3c4d, subnet-3c4d5e6f",
            "IamInstanceProfile": {
                "Arn": "arn:aws:iam::123456789012:instance-profile/my-iam-role"
            }
        }
    ]
  }

Output::

  {
    "SpotFleetRequestId": "sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE"
  }


**To request a Spot fleet in the Availability Zone with the lowest price**

This example command creates a Spot fleet request with two launch specifications that differ only by Availability Zone.
The Spot fleet launches the instances in the specified Availability Zone with the lowest price.
If your account supports EC2-VPC only, Amazon EC2 launches the Spot instances in the default subnet of the Availability Zone. 
If your account supports EC2-Classic, Amazon EC2 launches the instances in EC2-Classic in the Availability Zone. 

Command::

  aws ec2 request-spot-fleet --spot-fleet-request-config file://config.json
  
Config.json:: 

  {
    "SpotPrice": "0.04", 
    "TargetCapacity": 2,
    "IamFleetRole": "arn:aws:iam::123456789012:role/my-spot-fleet-role",
    "LaunchSpecifications": [
        {
            "ImageId": "ami-1a2b3c4d",
            "KeyName": "my-key-pair",
            "SecurityGroups": [
                {
                    "GroupId": "sg-1a2b3c4d"
                }
            ],
            "InstanceType": "m3.medium",
            "Placement": {
                "AvailabilityZone": "us-west-2a, us-west-2b"
            },
            "IamInstanceProfile": {
                "Arn": "arn:aws:iam::123456789012:instance-profile/my-iam-role"
            }
        }
    ]
  }

**To launch Spot instances in a subnet and assign them public IP addresses**

This example command assigns public addresses to instances launched in a nondefault VPC. 
Note that when you specify a network interface, you must include the subnet ID and security group ID
using the network interface.

Command::

  aws ec2 request-spot-fleet --spot-fleet-request-config file://config.json
  
Config.json:: 

  {
    "SpotPrice": "0.04", 
    "TargetCapacity": 2,
    "IamFleetRole": "arn:aws:iam::123456789012:role/my-spot-fleet-role",
    "LaunchSpecifications": [
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
                "Arn": "arn:aws:iam::880185128111:instance-profile/my-iam-role"
            }
        }
    ]
  }

**To request a Spot fleet using the diversified allocation strategy**

This example command creates a Spot fleet request that launches 30 instances using the diversified allocation strategy.
The launch specifications differ by instance type. The Spot fleet distributes the instances
across the launch specifications such that there are 10 instances of each type.

Command::

  aws ec2 request-spot-fleet --spot-fleet-request-config file://config.json
  
Config.json:: 

  {
    "SpotPrice": "0.70", 
    "TargetCapacity": 30,
    "AllocationStrategy": "diversified",
    "IamFleetRole": "arn:aws:iam::123456789012:role/my-spot-fleet-role",
    "LaunchSpecifications": [
        {
            "ImageId": "ami-1a2b3c4d",
            "InstanceType": "c4.2xlarge",
            "SubnetId": "subnet-1a2b3c4d"
        },
        {
            "ImageId": "ami-1a2b3c4d",
            "InstanceType": "m3.2xlarge",
            "SubnetId": "subnet-1a2b3c4d"
        },
        {
            "ImageId": "ami-1a2b3c4d",
            "InstanceType": "r3.2xlarge",
            "SubnetId": "subnet-1a2b3c4d"
        }
    ]
  }

For more information, see `Spot Fleet Requests`_ in the *Amazon Elastic Compute Cloud User Guide*.

.. _`Spot Fleet Requests`: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-fleet-requests.html



======
Output
======

SpotFleetRequestId -> (string)

  

  The ID of the Spot fleet request.

  

  



.. _Spot Fleet Requests: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-fleet-requests.html
