[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway delete-snapshot-schedule:


************************
delete-snapshot-schedule
************************



===========
Description
===========



Deletes a snapshot of a volume.

 

You can take snapshots of your gateway volumes on a scheduled or ad hoc basis. This API action enables you to delete a snapshot schedule for a volume. For more information, see `Working with Snapshots <http://docs.aws.amazon.com/storagegateway/latest/userguide/WorkingWithSnapshots.html>`_ . In the ``delete-snapshot-schedule`` request, you identify the volume by providing its Amazon Resource Name (ARN). 

 

.. note::

   

  To list or delete a snapshot, you must use the Amazon EC2 API. in *Amazon Elastic Compute Cloud API Reference* .

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/DeleteSnapshotSchedule>`_


========
Synopsis
========

::

    delete-snapshot-schedule
  --volume-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--volume-arn`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

VolumeARN -> (string)

  

  

