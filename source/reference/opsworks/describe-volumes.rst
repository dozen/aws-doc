[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-volumes:


****************
describe-volumes
****************



===========
Description
===========



Describes an instance's Amazon EBS volumes.

 

.. note::

   

  This call accepts only one resource-identifying parameter.

   

 

 **Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DescribeVolumes>`_


========
Synopsis
========

::

    describe-volumes
  [--instance-id <value>]
  [--stack-id <value>]
  [--raid-array-id <value>]
  [--volume-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-id`` (string)


  The instance ID. If you use this parameter, ``describe-volumes`` returns descriptions of the volumes associated with the specified instance.

  

``--stack-id`` (string)


  A stack ID. The action describes the stack's registered Amazon EBS volumes.

  

``--raid-array-id`` (string)


  The RAID array ID. If you use this parameter, ``describe-volumes`` returns descriptions of the volumes associated with the specified RAID array.

  

``--volume-ids`` (list)


  Am array of volume IDs. If you use this parameter, ``describe-volumes`` returns descriptions of the specified volumes. Otherwise, it returns a description of every volume.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a stack's volumes**

The following example describes a stack's EBS volumes. ::

  aws opsworks --region us-east-1 describe-volumes --stack-id 8c428b08-a1a1-46ce-a5f8-feddc43771b8

*Output*::

  {
    "Volumes": [
      {
        "Status": "in-use",
        "AvailabilityZone": "us-west-2a",
        "Name": "CLITest",
        "InstanceId": "dfe18b02-5327-493d-91a4-c5c0c448927f",
        "VolumeType": "standard",
        "VolumeId": "56b66fbd-e1a1-4aff-9227-70f77118d4c5",
        "Device": "/dev/sdi",
        "Ec2VolumeId": "vol-295c1638",
        "MountPoint": "/mnt/myvolume",
        "Size": 1
      }
    ]
  }

**More Information**

For more information, see `Resource Management`_ in the *AWS OpsWorks User Guide*.

.. _`Resource Management`: http://docs.aws.amazon.com/opsworks/latest/userguide/resources.html



======
Output
======

Volumes -> (list)

  

  An array of volume IDs.

  

  (structure)

    

    Describes an instance's Amazon EBS volume.

    

    VolumeId -> (string)

      

      The volume ID.

      

      

    Ec2VolumeId -> (string)

      

      The Amazon EC2 volume ID.

      

      

    Name -> (string)

      

      The volume name.

      

      

    RaidArrayId -> (string)

      

      The RAID array ID.

      

      

    InstanceId -> (string)

      

      The instance ID.

      

      

    Status -> (string)

      

      The value returned by `describe-volumes <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/ApiReference-query-DescribeVolumes.html>`_ .

      

      

    Size -> (integer)

      

      The volume size.

      

      

    Device -> (string)

      

      The device name.

      

      

    MountPoint -> (string)

      

      The volume mount point. For example, "/mnt/disk1".

      

      

    Region -> (string)

      

      The AWS region. For more information about AWS regions, see `Regions and Endpoints <http://docs.aws.amazon.com/general/latest/gr/rande.html>`_ .

      

      

    AvailabilityZone -> (string)

      

      The volume Availability Zone. For more information, see `Regions and Endpoints <http://docs.aws.amazon.com/general/latest/gr/rande.html>`_ .

      

      

    VolumeType -> (string)

      

      The volume type, standard or PIOPS.

      

      

    Iops -> (integer)

      

      For PIOPS volumes, the IOPS per disk.

      

      

    

  

