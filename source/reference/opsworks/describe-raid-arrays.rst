[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-raid-arrays:


********************
describe-raid-arrays
********************



===========
Description
===========



Describe an instance's RAID arrays.

 

.. note::

   

  You must specify at least one of the parameters.

   

 

**Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    describe-raid-arrays
  [--instance-id <value>]
  [--stack-id <value>]
  [--raid-array-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-id`` (string)


  The instance ID. If you use this parameter, ``describe-raid-arrays`` returns descriptions of the RAID arrays associated with the specified instance. 

  

``--stack-id`` (string)


  The stack ID.

  

``--raid-array-ids`` (list)


  An array of RAID array IDs. If you use this parameter, ``describe-raid-arrays`` returns descriptions of the specified arrays. Otherwise, it returns a description of every array.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe RAID arrays**

The following example describes the RAID arrays attached to the instances in a specified stack. ::

  aws opsworks --region us-east-1 describe-raid-arrays --stack-id d72553d4-8727-448c-9b00-f024f0ba1b06

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: The following is the output for a stack with one RAID array. ::

  {
    "RaidArrays": [
      {
        "StackId": "d72553d4-8727-448c-9b00-f024f0ba1b06", 
        "AvailabilityZone": "us-west-2a", 
        "Name": "Created for php-app1", 
        "NumberOfDisks": 2, 
        "InstanceId": "9f14adbc-ced5-43b6-bf01-e7d0db6cf2f7", 
        "RaidLevel": 0, 
        "VolumeType": "standard", 
        "RaidArrayId": "f2d4e470-5972-4676-b1b8-bae41ec3e51c", 
        "Device": "/dev/md0", 
        "MountPoint": "/mnt/workspace", 
        "CreatedAt": "2015-02-26T23:53:09+00:00", 
        "Size": 100
      } 
    ]
  }

For more information, see `EBS Volumes`_ in the *AWS OpsWorks User Guide*.

.. _`EBS Volumes`: http://docs.aws.amazon.com/opsworks/latest/userguide/workinglayers-basics-edit.html#workinglayers-basics-edit-ebs



======
Output
======

RaidArrays -> (list)

  

  A ``RaidArrays`` object that describes the specified RAID arrays.

  

  (structure)

    

    Describes an instance's RAID array.

    

    RaidArrayId -> (string)

      

      The array ID.

      

      

    InstanceId -> (string)

      

      The instance ID.

      

      

    Name -> (string)

      

      The array name.

      

      

    RaidLevel -> (integer)

      

      The `RAID level`_ .

      

      

    NumberOfDisks -> (integer)

      

      The number of disks in the array.

      

      

    Size -> (integer)

      

      The array's size.

      

      

    Device -> (string)

      

      The array's Linux device. For example /dev/mdadm0.

      

      

    MountPoint -> (string)

      

      The array's mount point.

      

      

    AvailabilityZone -> (string)

      

      The array's Availability Zone. For more information, see `Regions and Endpoints`_ .

      

      

    CreatedAt -> (string)

      

      When the RAID array was created.

      

      

    StackId -> (string)

      

      The stack ID.

      

      

    VolumeType -> (string)

      

      The volume type, standard or PIOPS.

      

      

    Iops -> (integer)

      

      For PIOPS volumes, the IOPS per disk.

      

      

    

  



.. _RAID level: http://en.wikipedia.org/wiki/Standard_RAID_levels
.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
.. _Regions and Endpoints: http://docs.aws.amazon.com/general/latest/gr/rande.html
