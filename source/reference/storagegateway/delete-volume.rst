[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway delete-volume:


*************
delete-volume
*************



===========
Description
===========



This operation deletes the specified gateway volume that you previously created using the  create-cached-iscsi-volume or  create-stored-iscsi-volume API. For gateway-stored volumes, the local disk that was configured as the storage volume is not deleted. You can reuse the local disk to create another storage volume. 

 

Before you delete a gateway volume, make sure there are no iSCSI connections to the volume you are deleting. You should also make sure there is no snapshot in progress. You can use the Amazon Elastic Compute Cloud (Amazon EC2) API to query snapshots on the volume you are deleting and check the snapshot status. For more information, go to `DescribeSnapshots`_ in the *Amazon Elastic Compute Cloud API Reference* .

 

In the request, you must provide the Amazon Resource Name (ARN) of the storage volume you want to delete.



========
Synopsis
========

::

    delete-volume
  --volume-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--volume-arn`` (string)


  The Amazon Resource Name (ARN) of the volume. Use the  list-volumes operation to return a list of gateway volumes.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

VolumeARN -> (string)

  

  The Amazon Resource Name (ARN) of the storage volume that was deleted. It is the same ARN you provided in the request.

  

  



.. _DescribeSnapshots: http://docs.aws.amazon.com/AWSEC2/latest/APIReference/ApiReference-query-DescribeSnapshots.html
