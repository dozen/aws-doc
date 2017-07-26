[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway update-snapshot-schedule:


************************
update-snapshot-schedule
************************



===========
Description
===========



This operation updates a snapshot schedule configured for a gateway volume.

 

The default snapshot schedule for volume is once every 24 hours, starting at the creation time of the volume. You can use this API to change the snapshot schedule configured for the volume.

 

In the request you must identify the gateway volume whose snapshot schedule you want to update, and the schedule information, including when you want the snapshot to begin on a day and the frequency (in hours) of snapshots.



========
Synopsis
========

::

    update-snapshot-schedule
  --volume-arn <value>
  --start-at <value>
  --recurrence-in-hours <value>
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--volume-arn`` (string)


  The Amazon Resource Name (ARN) of the volume. Use the  list-volumes operation to return a list of gateway volumes.

  

``--start-at`` (integer)


  The hour of the day at which the snapshot schedule begins represented as *hh* , where *hh* is the hour (0 to 23). The hour of the day is in the time zone of the gateway.

  

``--recurrence-in-hours`` (integer)


  Frequency of snapshots. Specify the number of hours between snapshots.

  

``--description`` (string)


  Optional description of the snapshot that overwrites the existing description.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

VolumeARN -> (string)

  

  

