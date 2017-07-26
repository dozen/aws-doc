[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway create-snapshot:


***************
create-snapshot
***************



===========
Description
===========



Initiates a snapshot of a volume.

 

AWS Storage Gateway provides the ability to back up point-in-time snapshots of your data to Amazon Simple Storage (S3) for durable off-site recovery, as well as import the data to an Amazon Elastic Block Store (EBS) volume in Amazon Elastic Compute Cloud (EC2). You can take snapshots of your gateway volume on a scheduled or ad-hoc basis. This API enables you to take ad-hoc snapshot. For more information, see `Editing a Snapshot Schedule <http://docs.aws.amazon.com/storagegateway/latest/userguide/managing-volumes.html#SchedulingSnapshot>`_ .

 

In the create-snapshot request you identify the volume by providing its Amazon Resource Name (ARN). You must also provide description for the snapshot. When AWS Storage Gateway takes the snapshot of specified volume, the snapshot and description appears in the AWS Storage Gateway Console. In response, AWS Storage Gateway returns you a snapshot ID. You can use this snapshot ID to check the snapshot progress or later use it when you want to create a volume from a snapshot. This operation is only supported in stored and cached volume gateway architecture.

 

.. note::

   

  To list or delete a snapshot, you must use the Amazon EC2 API. For more information, see DescribeSnapshots or DeleteSnapshot in the `EC2 API reference <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_Operations.html>`_ .

   

 

.. warning::

   

  Volume and snapshot IDs are changing to a longer length ID format. For more information, see the important note on the `Welcome <http://docs.aws.amazon.com/storagegateway/latest/APIReference/Welcome.html>`_ page.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/CreateSnapshot>`_


========
Synopsis
========

::

    create-snapshot
  --volume-arn <value>
  --snapshot-description <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--volume-arn`` (string)


  The Amazon Resource Name (ARN) of the volume. Use the  list-volumes operation to return a list of gateway volumes.

  

``--snapshot-description`` (string)


  Textual description of the snapshot that appears in the Amazon EC2 console, Elastic Block Store snapshots panel in the **Description** field, and in the AWS Storage Gateway snapshot **Details** pane, **Description** field

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

VolumeARN -> (string)

  

  The Amazon Resource Name (ARN) of the volume of which the snapshot was taken.

  

  

SnapshotId -> (string)

  

  The snapshot ID that is used to refer to the snapshot in future operations such as describing snapshots (Amazon Elastic Compute Cloud API ``DescribeSnapshots`` ) or creating a volume from a snapshot ( create-stored-iscsi-volume ).

  

  

