[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-images:


***************
describe-images
***************



===========
Description
===========



Describes one or more of the images (AMIs, AKIs, and ARIs) available to you. Images available to you include public images, private images that you own, and private images owned by other AWS accounts but for which you have explicit launch permissions.

 

.. note::

   

  Deregistered images are included in the returned results for an unspecified interval after deregistration.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeImages>`_


========
Synopsis
========

::

    describe-images
  [--executable-users <value>]
  [--filters <value>]
  [--image-ids <value>]
  [--owners <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--executable-users`` (list)


  Scopes the images by users with explicit launch permissions. Specify an AWS account ID, ``self`` (the sender of the request), or ``all`` (public AMIs).

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``architecture`` - The image architecture (``i386`` | ``x86_64`` ). 
   
  * ``block-device-mapping.delete-on-termination`` - A dry-run value that indicates whether the Amazon EBS volume is deleted on instance termination. 
   
  * ``block-device-mapping.device-name`` - The device name for the EBS volume (for example, ``/dev/sdh`` ). 
   
  * ``block-device-mapping.snapshot-id`` - The ID of the snapshot used for the EBS volume. 
   
  * ``block-device-mapping.volume-size`` - The volume size of the EBS volume, in GiB. 
   
  * ``block-device-mapping.volume-type`` - The volume type of the EBS volume (``gp2`` | ``io1`` | ``st1`` | ``sc1`` | ``standard`` ). 
   
  * ``description`` - The description of the image (provided during image creation). 
   
  * ``ena-support`` - A dry-run that indicates whether enhanced networking with ENA is enabled. 
   
  * ``hypervisor`` - The hypervisor type (``ovm`` | ``xen`` ). 
   
  * ``image-id`` - The ID of the image. 
   
  * ``image-type`` - The image type (``machine`` | ``kernel`` | ``ramdisk`` ). 
   
  * ``is-public`` - A dry-run that indicates whether the image is public. 
   
  * ``kernel-id`` - The kernel ID. 
   
  * ``manifest-location`` - The location of the image manifest. 
   
  * ``name`` - The name of the AMI (provided during image creation). 
   
  * ``owner-alias`` - String value from an Amazon-maintained list (``amazon`` | ``aws-marketplace`` | ``microsoft`` ) of snapshot owners. Not to be confused with the user-configured AWS account alias, which is set from the IAM console. 
   
  * ``owner-id`` - The AWS account ID of the image owner. 
   
  * ``platform`` - The platform. To only list Windows-based AMIs, use ``windows`` . 
   
  * ``product-code`` - The product code. 
   
  * ``product-code.type`` - The type of the product code (``devpay`` | ``marketplace`` ). 
   
  * ``ramdisk-id`` - The RAM disk ID. 
   
  * ``root-device-name`` - The name of the root device volume (for example, ``/dev/sda1`` ). 
   
  * ``root-device-type`` - The type of the root device volume (``ebs`` | ``instance-store`` ). 
   
  * ``state`` - The state of the image (``available`` | ``pending`` | ``failed`` ). 
   
  * ``state-reason-code`` - The reason code for the state change. 
   
  * ``state-reason-message`` - The message for the state change. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. Specify the key of the tag in the filter name and the value of the tag in the filter value. For example, for the tag Purpose=X, specify ``tag:Purpose`` for the filter name and ``X`` for the filter value. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the tag-value filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``virtualization-type`` - The virtualization type (``paravirtual`` | ``hvm`` ). 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--image-ids`` (list)


  One or more image IDs.

   

  Default: Describes all images available to you.

  



Syntax::

  "string" "string" ...



``--owners`` (list)


  Filters the images by the owner. Specify an AWS account ID, ``self`` (owner is the sender of the request), or an AWS owner alias (valid values are ``amazon`` | ``aws-marketplace`` | ``microsoft`` ). Omitting this option returns all images for which you have launch permissions, regardless of ownership.

  



Syntax::

  "string" "string" ...



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a specific AMI**

This example describes the specified AMI.

Command::

  aws ec2 describe-images --image-ids ami-5731123e

Output::

  {
      "Images": [
          {
              "VirtualizationType": "paravirtual",
              "Name": "My server",
              "Hypervisor": "xen",
              "ImageId": "ami-5731123e",
              "RootDeviceType": "ebs",
              "State": "available",
              "BlockDeviceMappings": [
                  {
                      "DeviceName": "/dev/sda1",
                      "Ebs": {
                          "DeleteOnTermination": true,
                          "SnapshotId": "snap-1234567890abcdef0",
                          "VolumeSize": 8,
                          "VolumeType": "standard"
                      }
                  }
              ],
              "Architecture": "x86_64",
              "ImageLocation": "123456789012/My server",
              "KernelId": "aki-88aa75e1",
              "OwnerId": "123456789012",
              "RootDeviceName": "/dev/sda1",
              "Public": false,
              "ImageType": "machine",
              "Description": "An AMI for my server"
          }
      ]
  }

**To describe Windows AMIs from Amazon that are backed by Amazon EBS**

This example describes Windows AMIs provided by Amazon that are backed by Amazon EBS.

Command::

  aws ec2 describe-images --owners amazon --filters "Name=platform,Values=windows" "Name=root-device-type,Values=ebs"

**To describe tagged AMIs**

This example describes all AMIs that have the tag ``Custom=Linux1`` or ``Custom=Ubuntu1``. The output is filtered to display only the AMI IDs.

Command::

  aws ec2 describe-images --filters Name=tag-key,Values=Custom Name=tag-value,Values=Linux1,Ubuntu1 --query 'Images[*].{ID:ImageId}'

Output::

   [
     {
        "ID": "ami-1a2b3c4d"
     }, 
     {
        "ID": "ami-ab12cd34"
     }
   ]


======
Output
======

Images -> (list)

  

  Information about one or more images.

  

  (structure)

    

    Describes an image.

    

    Architecture -> (string)

      

      The architecture of the image.

      

      

    CreationDate -> (string)

      

      The date and time the image was created.

      

      

    ImageId -> (string)

      

      The ID of the AMI.

      

      

    ImageLocation -> (string)

      

      The location of the AMI.

      

      

    ImageType -> (string)

      

      The type of image.

      

      

    Public -> (boolean)

      

      Indicates whether the image has public launch permissions. The value is ``true`` if this image has public launch permissions or ``false`` if it has only implicit and explicit launch permissions.

      

      

    KernelId -> (string)

      

      The kernel associated with the image, if any. Only applicable for machine images.

      

      

    OwnerId -> (string)

      

      The AWS account ID of the image owner.

      

      

    Platform -> (string)

      

      The value is ``Windows`` for Windows AMIs; otherwise blank.

      

      

    ProductCodes -> (list)

      

      Any product codes associated with the AMI.

      

      (structure)

        

        Describes a product code.

        

        ProductCodeId -> (string)

          

          The product code.

          

          

        ProductCodeType -> (string)

          

          The type of product code.

          

          

        

      

    RamdiskId -> (string)

      

      The RAM disk associated with the image, if any. Only applicable for machine images.

      

      

    State -> (string)

      

      The current state of the AMI. If the state is ``available`` , the image is successfully registered and can be used to launch an instance.

      

      

    BlockDeviceMappings -> (list)

      

      Any block device mapping entries.

      

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

          

          

        

      

    Description -> (string)

      

      The description of the AMI that was provided during image creation.

      

      

    EnaSupport -> (boolean)

      

      Specifies whether enhanced networking with ENA is enabled.

      

      

    Hypervisor -> (string)

      

      The hypervisor type of the image.

      

      

    ImageOwnerAlias -> (string)

      

      The AWS account alias (for example, ``amazon`` , ``self`` ) or the AWS account ID of the AMI owner.

      

      

    Name -> (string)

      

      The name of the AMI that was provided during image creation.

      

      

    RootDeviceName -> (string)

      

      The device name of the root device (for example, ``/dev/sda1`` or ``/dev/xvda`` ).

      

      

    RootDeviceType -> (string)

      

      The type of root device used by the AMI. The AMI can use an EBS volume or an instance store volume.

      

      

    SriovNetSupport -> (string)

      

      Specifies whether enhanced networking with the Intel 82599 Virtual Function interface is enabled.

      

      

    StateReason -> (structure)

      

      The reason for the state change.

      

      Code -> (string)

        

        The reason code for the state change.

        

        

      Message -> (string)

        

        The message for the state change.

         

         
        * ``Server.InsufficientInstanceCapacity`` : There was insufficient instance capacity to satisfy the launch request. 
         
        * ``Server.InternalError`` : An internal error occurred during instance launch, resulting in termination. 
         
        * ``Server.ScheduledStop`` : The instance was stopped due to a scheduled retirement. 
         
        * ``Server.SpotInstanceTermination`` : A Spot instance was terminated due to an increase in the market price. 
         
        * ``Client.InternalError`` : A client error caused the instance to terminate on launch. 
         
        * ``Client.InstanceInitiatedShutdown`` : The instance was shut down using the ``shutdown -h`` command from the instance. 
         
        * ``Client.UserInitiatedShutdown`` : The instance was shut down using the Amazon EC2 API. 
         
        * ``Client.VolumeLimitExceeded`` : The limit on the number of EBS volumes or total storage was exceeded. Decrease usage or request an increase in your limits. 
         
        * ``Client.InvalidSnapshot.NotFound`` : The specified snapshot was not found. 
         

        

        

      

    Tags -> (list)

      

      Any tags assigned to the image.

      

      (structure)

        

        Describes a tag.

        

        Key -> (string)

          

          The key of the tag.

           

          Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:``  

          

          

        Value -> (string)

          

          The value of the tag.

           

          Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

          

          

        

      

    VirtualizationType -> (string)

      

      The type of virtualization of the AMI.

      

      

    

  

