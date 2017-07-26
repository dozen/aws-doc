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

 

You must launch a Scheduled Instance during its scheduled time period. You can't stop or reboot a Scheduled Instance, but you can terminate it as needed. If you terminate a Scheduled Instance before the current scheduled time period ends, you can launch it again after a few minutes.



========
Synopsis
========

::

    run-scheduled-instances
  [--dry-run | --no-dry-run]
  [--client-token <value>]
  [--instance-count <value>]
  --scheduled-instance-id <value>
  --launch-specification <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--client-token`` (string)


  Unique, case-sensitive identifier that ensures the idempotency of the request. For more information, see `Ensuring Idempotency`_ .

  

``--instance-count`` (integer)


  The number of instances.

   

  Default: 1

  

``--scheduled-instance-id`` (string)


  The Scheduled Instance ID.

  

``--launch-specification`` (structure)


  The launch specification.

  



JSON Syntax::

  {
    "ImageId": "string",
    "KeyName": "string",
    "SecurityGroupIds": ["string", ...],
    "UserData": "string",
    "Placement": {
      "AvailabilityZone": "string",
      "GroupName": "string"
    },
    "KernelId": "string",
    "InstanceType": "string",
    "RamdiskId": "string",
    "BlockDeviceMappings": [
      {
        "DeviceName": "string",
        "NoDevice": "string",
        "VirtualName": "string",
        "Ebs": {
          "SnapshotId": "string",
          "VolumeSize": integer,
          "DeleteOnTermination": true|false,
          "VolumeType": "string",
          "Iops": integer,
          "Encrypted": true|false
        }
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
        "PrivateIpAddressConfigs": [
          {
            "PrivateIpAddress": "string",
            "Primary": true|false
          }
          ...
        ],
        "SecondaryPrivateIpAddressCount": integer,
        "AssociatePublicIpAddress": true|false,
        "Groups": ["string", ...],
        "DeleteOnTermination": true|false
      }
      ...
    ],
    "IamInstanceProfile": {
      "Arn": "string",
      "Name": "string"
    },
    "EbsOptimized": true|false
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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
        "i-1a2b3c4d"
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
        "i-1a2b3c4d"
    ]
  }


======
Output
======

InstanceIdSet -> (list)

  

  The IDs of the newly launched instances.

  

  (string)

    

    

  



.. _Ensuring Idempotency: http://docs.aws.amazon.com/AWSEC2/latest/APIReference/Run_Instance_Idempotency.html
