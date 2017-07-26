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

 

For more information, see `Spot Fleet Requests <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-fleet-requests.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/RequestSpotFleet>`_


========
Synopsis
========

::

    request-spot-fleet
  [--dry-run | --no-dry-run]
  --spot-fleet-request-config <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--spot-fleet-request-config`` (structure)


  The configuration for the Spot fleet request.

  



JSON Syntax::

  {
    "AllocationStrategy": "lowestPrice"|"diversified",
    "ClientToken": "string",
    "ExcessCapacityTerminationPolicy": "noTermination"|"default",
    "FulfilledCapacity": double,
    "IamFleetRole": "string",
    "LaunchSpecifications": [
      {
        "SecurityGroups": [
          {
            "GroupName": "string",
            "GroupId": "string"
          }
          ...
        ],
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
        "SpotPrice": "string",
        "SubnetId": "string",
        "UserData": "string",
        "WeightedCapacity": double,
        "TagSpecifications": [
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
      }
      ...
    ],
    "SpotPrice": "string",
    "TargetCapacity": integer,
    "TerminateInstancesWithExpiration": true|false,
    "Type": "request"|"maintain",
    "ValidFrom": timestamp,
    "ValidUntil": timestamp,
    "ReplaceUnhealthyInstances": true|false
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  

