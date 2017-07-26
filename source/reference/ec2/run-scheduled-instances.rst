[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 run-scheduled-instances:


***********************
run-scheduled-instances
***********************



===========
Description
===========



Launches the specified Scheduled Instances.

 

Before you can launch a Scheduled Instance, you must purchase it and obtain an identifier using  purchase-scheduled-instances .

 

You must launch a Scheduled Instance during its scheduled time period. You can't stop or reboot a Scheduled Instance, but you can terminate it as needed. If you terminate a Scheduled Instance before the current scheduled time period ends, you can launch it again after a few minutes. For more information, see `Scheduled Instances <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-scheduled-instances.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/RunScheduledInstances>`_


========
Synopsis
========

::

    run-scheduled-instances
  [--client-token <value>]
  [--dry-run | --no-dry-run]
  [--instance-count <value>]
  --launch-specification <value>
  --scheduled-instance-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--client-token`` (string)


  Unique, case-sensitive identifier that ensures the idempotency of the request. For more information, see `Ensuring Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/Run_Instance_Idempotency.html>`_ .

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instance-count`` (integer)


  The number of instances.

   

  Default: 1

  

``--launch-specification`` (structure)


  The launch specification. You must match the instance type, Availability Zone, network, and platform of the schedule that you purchased.

  



JSON Syntax::

  {
    "BlockDeviceMappings": [
      {
        "DeviceName": "string",
        "Ebs": {
          "DeleteOnTermination": true|false,
          "Encrypted": true|false,
          "Iops": integer,
          "SnapshotId": "string",
          "VolumeSize": integer,
          "VolumeType": "string"
        },
        "NoDevice": "string",
        "VirtualName": "string"
      }
      ...
    ],
    "EbsOptimized": true|false,
    "IamInstanceProfile": {
      "Arn": "string",
      "Name": "string"
    },
    "ImageId": "string",
    "InstanceType": "string",
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
        "PrivateIpAddressConfigs": [
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
      "GroupName": "string"
    },
    "RamdiskId": "string",
    "SecurityGroupIds": ["string", ...],
    "SubnetId": "string",
    "UserData": "string"
  }



``--scheduled-instance-id`` (string)


  The Scheduled Instance ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To launch a Scheduled Instance**

This example launches the specified Scheduled Instance in a VPC.

Command::

  aws ec2 run-scheduled-instances --scheduled-instance-id sci-1234-1234-1234-1234-123456789012 --instance-count 1 --launch-specification file://launch-specification.json

Launch-specification.json::

  {
    "ImageId": "ami-12345678",
    "KeyName": "my-key-pair",
    "InstanceType": "c4.large",
    "NetworkInterfaces": [
      {
          "DeviceIndex": 0,
          "SubnetId": "subnet-12345678",
          "AssociatePublicIpAddress": true,
          "Groups": ["sg-12345678"]
      }
    ],
    "IamInstanceProfile": {
        "Name": "my-iam-role"
    }
  }

Output::

  {
    "InstanceIdSet": [
        "i-1234567890abcdef0"
    ]
  }

This example launches the specified Scheduled Instance in EC2-Classic.

Command::

  aws ec2 run-scheduled-instances --scheduled-instance-id sci-1234-1234-1234-1234-123456789012 --instance-count 1 --launch-specification file://launch-specification.json

Launch-specification.json::

  {
    "ImageId": "ami-12345678",
    "KeyName": "my-key-pair",
    "SecurityGroupIds": ["sg-12345678"],
    "InstanceType": "c4.large",
    "Placement": {
      "AvailabilityZone": "us-west-2b"
    }
    "IamInstanceProfile": {
        "Name": "my-iam-role"
    }
  }

Output::

  {
    "InstanceIdSet": [
        "i-1234567890abcdef0"
    ]
  }


======
Output
======

InstanceIdSet -> (list)

  

  The IDs of the newly launched instances.

  

  (string)

    

    

  

