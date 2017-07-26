[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway create-snapshot-from-volume-recovery-point:


******************************************
create-snapshot-from-volume-recovery-point
******************************************



===========
Description
===========



This operation initiates a snapshot of a gateway from a volume recovery point. This operation is supported only for the gateway-cached volume architecture (see ).

 

A volume recovery point is a point in time at which all data of the volume is consistent and from which you can create a snapshot. To get a list of volume recovery point for gateway-cached volumes, use  list-volume-recovery-points .

 

In the ``create-snapshot-from-volume-recovery-point`` request, you identify the volume by providing its Amazon Resource Name (ARN). You must also provide a description for the snapshot. When AWS Storage Gateway takes a snapshot of the specified volume, the snapshot and its description appear in the AWS Storage Gateway console. In response, AWS Storage Gateway returns you a snapshot ID. You can use this snapshot ID to check the snapshot progress or later use it when you want to create a volume from a snapshot.

 

.. note::

   

  To list or delete a snapshot, you must use the Amazon EC2 API. For more information, in *Amazon Elastic Compute Cloud API Reference* .

   



========
Synopsis
========

::

    create-snapshot-from-volume-recovery-point
  --volume-arn <value>
  --snapshot-description <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--volume-arn`` (string)


``--snapshot-description`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

SnapshotId -> (string)

  

  

VolumeARN -> (string)

  

  

VolumeRecoveryPointTime -> (string)

  

  

