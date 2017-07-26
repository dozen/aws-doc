[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-volume:


*************
modify-volume
*************



===========
Description
===========



You can modify several parameters of an existing EBS volume, including volume size, volume type, and IOPS capacity. If your EBS volume is attached to a current-generation EC2 instance type, you may be able to apply these changes without stopping the instance or detaching the volume from it. For more information about modifying an EBS volume running Linux, see `Modifying the Size, IOPS, or Type of an EBS Volume on Linux <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-expand-volume.html>`_ . For more information about modifying an EBS volume running Windows, see `Modifying the Size, IOPS, or Type of an EBS Volume on Windows <http://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ebs-expand-volume.html>`_ . 

 

When you complete a resize operation on your volume, you need to extend the volume's file-system size to take advantage of the new storage capacity. For information about extending a Linux file system, see `Extending a Linux File System <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-expand-volume.html#recognize-expanded-volume-linux>`_ . For information about extending a Windows file system, see `Extending a Windows File System <http://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ebs-expand-volume.html#recognize-expanded-volume-windows>`_ . 

 

You can use CloudWatch Events to check the status of a modification to an EBS volume. For information about CloudWatch Events, see the `Amazon CloudWatch Events User Guide <http://docs.aws.amazon.com/AmazonCloudWatch/latest/events/>`_ . You can also track the status of a modification using the  describe-volumes-modifications API. For information about tracking status changes using either method, see `Monitoring Volume Modifications <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-expand-volume.html#monitoring_mods>`_ . 

 

.. note::

   

  With previous-generation instance types, resizing an EBS volume may require detaching and reattaching the volume or stopping and restarting the instance. For more information about modifying an EBS volume running Linux, see `Modifying the Size, IOPS, or Type of an EBS Volume on Linux <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-expand-volume.html>`_ . For more information about modifying an EBS volume running Windows, see `Modifying the Size, IOPS, or Type of an EBS Volume on Windows <http://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ebs-expand-volume.html>`_ .

   

 

.. note::

   

  If you reach the maximum volume modification rate per volume limit, you will need to wait at least six hours before applying further modifications to the affected EBS volume.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ModifyVolume>`_


========
Synopsis
========

::

    modify-volume
  [--dry-run | --no-dry-run]
  --volume-id <value>
  [--size <value>]
  [--volume-type <value>]
  [--iops <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--volume-id`` (string)


``--size`` (integer)


  Target size in GiB of the volume to be modified. Target volume size must be greater than or equal to than the existing size of the volume. For information about available EBS volume sizes, see `http\://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html>`_ .

   

  Default: If no size is specified, the existing size is retained. 

  

``--volume-type`` (string)


  Target EBS volume type of the volume to be modified

   

  The API does not support modifications for volume type ``standard`` . You also cannot change the type of a volume to ``standard`` . 

   

  Default: If no type is specified, the existing type is retained. 

  

  Possible values:

  
  *   ``standard``

  
  *   ``io1``

  
  *   ``gp2``

  
  *   ``sc1``

  
  *   ``st1``

  

  

``--iops`` (integer)


  Target IOPS rate of the volume to be modified.

   

  Only valid for Provisioned IOPS SSD (``io1`` ) volumes. For more information about ``io1`` IOPS configuration, see `http\://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html#EBSVolumeTypes_piops <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html#EBSVolumeTypes_piops>`_ .

   

  Default: If no IOPS value is specified, the existing value is retained. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

VolumeModification -> (structure)

  

  A  VolumeModification object.

  

  VolumeId -> (string)

    

    ID of the volume being modified.

    

    

  ModificationState -> (string)

    

    Current state of modification. Modification state is null for unmodified volumes. 

    

    

  StatusMessage -> (string)

    

    Generic status message on modification progress or failure.

    

    

  TargetSize -> (integer)

    

    Target size of the volume being modified.

    

    

  TargetIops -> (integer)

    

    Target IOPS rate of the volume being modified.

    

    

  TargetVolumeType -> (string)

    

    Target EBS volume type of the volume being modified.

    

    

  OriginalSize -> (integer)

    

    Original size of the volume being modified.

    

    

  OriginalIops -> (integer)

    

    Original IOPS rate of the volume being modified.

    

    

  OriginalVolumeType -> (string)

    

    Original EBS volume type of the volume being modified.

    

    

  Progress -> (long)

    

    Modification progress from 0 to 100%.

    

    

  StartTime -> (timestamp)

    

    Modification start time 

    

    

  EndTime -> (timestamp)

    

    Modification completion or failure time.

    

    

  

