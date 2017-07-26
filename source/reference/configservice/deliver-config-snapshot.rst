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
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/DeliverConfigSnapshot>`_


========
Synopsis
========

::

    deliver-config-snapshot
  --delivery-channel-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--delivery-channel-name`` (string)


  The name of the delivery channel through which the snapshot is delivered.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  

