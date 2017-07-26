[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-image-attribute:


************************
describe-image-attribute
************************



===========
Description
===========



Describes the specified attribute of the specified AMI. You can specify only one attribute at a time.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeImageAttribute>`_


========
Synopsis
========

::

    describe-image-attribute
  --attribute <value>
  --image-id <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

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

  

  

``--image-id`` (string)


  The ID of the AMI.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      

    

  

ImageId -> (string)

  

  The ID of the AMI.

  

  

LaunchPermissions -> (list)

  

  One or more launch permissions.

  

  (structure)

    

    Describes a launch permission.

    

    Group -> (string)

      

      The name of the group.

      

      

    UserId -> (string)

      

      The AWS account ID.

      

      

    

  

ProductCodes -> (list)

  

  One or more product codes.

  

  (structure)

    

    Describes a product code.

    

    ProductCodeId -> (string)

      

      The product code.

      

      

    ProductCodeType -> (string)

      

      The type of product code.

      

      

    

  

Description -> (structure)

  

  A description for the AMI.

  

  Value -> (string)

    

    The attribute value. Note that the value is case-sensitive.

    

    

  

KernelId -> (structure)

  

  The kernel ID.

  

  Value -> (string)

    

    The attribute value. Note that the value is case-sensitive.

    

    

  

RamdiskId -> (structure)

  

  The RAM disk ID.

  

  Value -> (string)

    

    The attribute value. Note that the value is case-sensitive.

    

    

  

SriovNetSupport -> (structure)

  

  Indicates whether enhanced networking with the Intel 82599 Virtual Function interface is enabled.

  

  Value -> (string)

    

    The attribute value. Note that the value is case-sensitive.

    

    

  

