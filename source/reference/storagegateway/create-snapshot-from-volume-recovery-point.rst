[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway create-snapshot-from-volume-recovery-point:


******************************************
create-snapshot-from-volume-recovery-point
******************************************



===========
Description
===========



Initiates a snapshot of a gateway from a volume recovery point. This operation is only supported in the cached volume gateway architecture.

 

A volume recovery point is a point in time at which all data of the volume is consistent and from which you can create a snapshot. To get a list of volume recovery point for cached volume gateway, use  list-volume-recovery-points .

 

In the ``create-snapshot-from-volume-recovery-point`` request, you identify the volume by providing its Amazon Resource Name (ARN). You must also provide a description for the snapshot. When the gateway takes a snapshot of the specified volume, the snapshot and its description appear in the AWS Storage Gateway console. In response, the gateway returns you a snapshot ID. You can use this snapshot ID to check the snapshot progress or later use it when you want to create a volume from a snapshot.

 

.. note::

   

  To list or delete a snapshot, you must use the Amazon EC2 API. For more information, in *Amazon Elastic Compute Cloud API Reference* .

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/CreateSnapshotFromVolumeRecoveryPoint>`_


========
Synopsis
========

::

    create-snapshot-from-volume-recovery-point
  --volume-arn <value>
  --snapshot-description <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--volume-arn`` (string)


``--snapshot-description`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SnapshotId -> (string)

  

  

VolumeARN -> (string)

  

  

VolumeRecoveryPointTime -> (string)

  

  

