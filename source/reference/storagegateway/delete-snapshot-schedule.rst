[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway delete-snapshot-schedule:


************************
delete-snapshot-schedule
************************



===========
Description
===========



This operation deletes a snapshot of a volume. 

 

You can take snapshots of your gateway volumes on a scheduled or ad-hoc basis. This API enables you to delete a snapshot schedule for a volume. For more information, see `Working with Snapshots`_ . In the ``delete-snapshot-schedule`` request, you identify the volume by providing its Amazon Resource Name (ARN). 

 

.. note::

   

  To list or delete a snapshot, you must use the Amazon EC2 API. in *Amazon Elastic Compute Cloud API Reference* .

   



========
Synopsis
========

::

    delete-snapshot-schedule
  --volume-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--volume-arn`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

VolumeARN -> (string)

  

  



.. _Working with Snapshots: http://docs.aws.amazon.com/storagegateway/latest/userguide/WorkingWithSnapshots.html
