[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice deliver-config-snapshot:


***********************
deliver-config-snapshot
***********************



===========
Description
===========



Schedules delivery of a configuration snapshot to the Amazon S3 bucket in the specified delivery channel. After the delivery has started, AWS Config sends following notifications using an Amazon SNS topic that you have specified.

 

 
* Notification of starting the delivery.
 
* Notification of delivery completed, if the delivery was successfully completed.
 
* Notification of delivery failure, if the delivery failed to complete.
 



========
Synopsis
========

::

    deliver-config-snapshot
  --delivery-channel-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--delivery-channel-name`` (string)


  The name of the delivery channel through which the snapshot is delivered.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To deliver a configuration snapshot**

The following command delivers a configuration snapshot to the Amazon S3 bucket that belongs to the default delivery channel::

    aws configservice deliver-config-snapshot --delivery-channel-name default

Output::
      
    {
        "configSnapshotId": "d0333b00-a683-44af-921e-examplefb794"
    }

======
Output
======

configSnapshotId -> (string)

  

  The ID of the snapshot that is being created.

  

  

