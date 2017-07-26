[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway create-snapshot:


***************
create-snapshot
***************



===========
Description
===========



This operation initiates a snapshot of a volume.

 

AWS Storage Gateway provides the ability to back up point-in-time snapshots of your data to Amazon Simple Storage (S3) for durable off-site recovery, as well as import the data to an Amazon Elastic Block Store (EBS) volume in Amazon Elastic Compute Cloud (EC2). You can take snapshots of your gateway volume on a scheduled or ad-hoc basis. This API enables you to take ad-hoc snapshot. For more information, see `Working With Snapshots in the AWS Storage Gateway Console`_ .

 

In the create-snapshot request you identify the volume by providing its Amazon Resource Name (ARN). You must also provide description for the snapshot. When AWS Storage Gateway takes the snapshot of specified volume, the snapshot and description appears in the AWS Storage Gateway Console. In response, AWS Storage Gateway returns you a snapshot ID. You can use this snapshot ID to check the snapshot progress or later use it when you want to create a volume from a snapshot.

 

.. note::

  To list or delete a snapshot, you must use the Amazon EC2 API. For more information, see DescribeSnapshots or DeleteSnapshot in the `EC2 API reference`_ .



========
Synopsis
========

::

    create-snapshot
  --volume-arn <value>
  --snapshot-description <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--volume-arn`` (string)


  The Amazon Resource Name (ARN) of the volume. Use the  list-volumes operation to return a list of gateway volumes.

  

``--snapshot-description`` (string)


  Textual description of the snapshot that appears in the Amazon EC2 console, Elastic Block Store snapshots panel in the **Description** field, and in the AWS Storage Gateway snapshot **Details** pane, **Description** field

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

VolumeARN -> (string)

  

  The Amazon Resource Name (ARN) of the volume of which the snapshot was taken.

  

  

SnapshotId -> (string)

  

  The snapshot ID that is used to refer to the snapshot in future operations such as describing snapshots (Amazon Elastic Compute Cloud API ``DescribeSnapshots`` ) or creating a volume from a snapshot ( create-stored-iscsi-volume ).

  

  



.. _EC2 API reference: http://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_Operations.html
.. _Working With Snapshots in the AWS Storage Gateway Console: http://docs.aws.amazon.com/storagegateway/latest/userguide/WorkingWithSnapshots.html
