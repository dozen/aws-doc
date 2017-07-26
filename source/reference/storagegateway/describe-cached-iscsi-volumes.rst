[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway describe-cached-iscsi-volumes:


*****************************
describe-cached-iscsi-volumes
*****************************



===========
Description
===========



Returns a description of the gateway volumes specified in the request. This operation is only supported in the cached volume gateway architecture.

 

The list of gateway volumes in the request must be from one gateway. In the response Amazon Storage Gateway returns volume information sorted by volume Amazon Resource Name (ARN).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/DescribeCachediSCSIVolumes>`_


========
Synopsis
========

::

    describe-cached-iscsi-volumes
  --volume-arns <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--volume-arns`` (list)




Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CachediSCSIVolumes -> (list)

  

  An array of objects where each object contains metadata about one cached volume.

  

  (structure)

    

    Describes an iSCSI cached volume.

    

    VolumeARN -> (string)

      

      The Amazon Resource Name (ARN) of the storage volume.

      

      

    VolumeId -> (string)

      

      The unique identifier of the volume, e.g. vol-AE4B946D.

      

      

    VolumeType -> (string)

      

      One of the VolumeType enumeration values that describes the type of the volume.

      

      

    VolumeStatus -> (string)

      

      One of the VolumeStatus values that indicates the state of the storage volume.

      

      

    VolumeSizeInBytes -> (long)

      

      The size of the volume in bytes.

      

      

    VolumeProgress -> (double)

      

      Represents the percentage complete if the volume is restoring or bootstrapping that represents the percent of data transferred. This field does not appear in the response if the cached volume is not restoring or bootstrapping.

      

      

    SourceSnapshotId -> (string)

      

      If the cached volume was created from a snapshot, this field contains the snapshot ID used, e.g. snap-78e22663. Otherwise, this field is not included.

      

      

    VolumeiSCSIAttributes -> (structure)

      

      An  VolumeiSCSIAttributes object that represents a collection of iSCSI attributes for one stored volume.

      

      TargetARN -> (string)

        

        The Amazon Resource Name (ARN) of the volume target.

        

        

      NetworkInterfaceId -> (string)

        

        The network interface identifier.

        

        

      NetworkInterfacePort -> (integer)

        

        The port used to communicate with iSCSI targets.

        

        

      LunNumber -> (integer)

        

        The logical disk number.

        

        

      ChapEnabled -> (boolean)

        

        Indicates whether mutual CHAP is enabled for the iSCSI target.

        

        

      

    CreatedDate -> (timestamp)

      

      The date the volume was created. Volumes created prior to March 28, 2017 don’t have this time stamp.

      

      

    

  

