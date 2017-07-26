[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-image-attribute:


************************
describe-image-attribute
************************



===========
Description
===========



Describes the specified attribute of the specified AMI. You can specify only one attribute at a time.



========
Synopsis
========

::

    describe-image-attribute
  [--dry-run | --no-dry-run]
  --image-id <value>
  --attribute <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--image-id`` (string)


  The ID of the AMI.

  

``--attribute`` (string)


  The AMI attribute.

   

  **Note** : Depending on your account privileges, the ``blockDeviceMapping`` attribute may return a ``Client.AuthFailure`` error. If this happens, use  describe-images to get information about the block device mapping for the AMI.

  

  Possible values:

  
  *   ``description``

  
  *   ``kernel``

  
  *   ``ramdisk``

  
  *   ``launchPermission``

  
  *   ``productCodes``

  
  *   ``blockDeviceMapping``

  
  *   ``sriovNetSupport``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe the launch permissions for an AMI**

This example describes the launch permissions for the specified AMI. 

Command::

  aws ec2 describe-image-attribute --image-id ami-5731123e --attribute launchPermission

Output::

  {
      "LaunchPermissions": [
          {
              "UserId": "123456789012"
          }
      ],
      "ImageId": "ami-5731123e",
  }

**To describe the product codes for an AMI**

This example describes the product codes for the specified AMI. Note that this AMI has no product codes.

Command::

  aws ec2 describe-image-attribute --image-id ami-5731123e --attribute productCodes

Output::

  {
      "ProductCodes": [],
      "ImageId": "ami-5731123e",
  }

======
Output
======

ImageId -> (string)

  

  The ID of the AMI.

  

  

LaunchPermissions -> (list)

  

  One or more launch permissions.

  

  (structure)

    

    Describes a launch permission.

    

    UserId -> (string)

      

      The AWS account ID.

      

      

    Group -> (string)

      

      The name of the group.

      

      

    

  

ProductCodes -> (list)

  

  One or more product codes.

  

  (structure)

    

    Describes a product code.

    

    ProductCodeId -> (string)

      

      The product code.

      

      

    ProductCodeType -> (string)

      

      The type of product code.

      

      

    

  

KernelId -> (structure)

  

  The kernel ID.

  

  Value -> (string)

    

    Valid values are case-sensitive and vary by action.

    

    

  

RamdiskId -> (structure)

  

  The RAM disk ID.

  

  Value -> (string)

    

    Valid values are case-sensitive and vary by action.

    

    

  

Description -> (structure)

  

  A description for the AMI.

  

  Value -> (string)

    

    Valid values are case-sensitive and vary by action.

    

    

  

SriovNetSupport -> (structure)

  

  The value to use for a resource attribute.

  

  Value -> (string)

    

    Valid values are case-sensitive and vary by action.

    

    

  

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

      

      

    

  



.. _Amazon EBS Volume Types: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html
