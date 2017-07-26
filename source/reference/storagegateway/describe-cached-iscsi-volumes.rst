[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway describe-cached-iscsi-volumes:


*****************************
describe-cached-iscsi-volumes
*****************************



===========
Description
===========



This operation returns a description of the gateway volumes specified in the request. This operation is supported only for the gateway-cached volume architecture.

 

The list of gateway volumes in the request must be from one gateway. In the response Amazon Storage Gateway returns volume information sorted by volume Amazon Resource Name (ARN). 



========
Synopsis
========

::

    describe-cached-iscsi-volumes
  --volume-arns <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--volume-arns`` (list)




Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

CachediSCSIVolumes -> (list)

  

  An array of objects where each object contains metadata about one cached volume.

  

  (structure)

    

    VolumeARN -> (string)

      

      

    VolumeId -> (string)

      

      

    VolumeType -> (string)

      

      

    VolumeStatus -> (string)

      

      

    VolumeSizeInBytes -> (long)

      

      

    VolumeProgress -> (double)

      

      

    SourceSnapshotId -> (string)

      

      

    VolumeiSCSIAttributes -> (structure)

      

      Lists iSCSI information about a volume.

      

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

        

        

      

    

  

