[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway delete-volume:


*************
delete-volume
*************



===========
Description
===========



Deletes the specified storage volume that you previously created using the  create-cached-iscsi-volume or  create-stored-iscsi-volume API. This operation is only supported in the cached volume and stored volume architectures. For stored volume gateways, the local disk that was configured as the storage volume is not deleted. You can reuse the local disk to create another storage volume. 

 

Before you delete a volume, make sure there are no iSCSI connections to the volume you are deleting. You should also make sure there is no snapshot in progress. You can use the Amazon Elastic Compute Cloud (Amazon EC2) API to query snapshots on the volume you are deleting and check the snapshot status. For more information, go to `DescribeSnapshots <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/ApiReference-query-DescribeSnapshots.html>`_ in the *Amazon Elastic Compute Cloud API Reference* .

 

In the request, you must provide the Amazon Resource Name (ARN) of the storage volume you want to delete.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/DeleteVolume>`_


========
Synopsis
========

::

    delete-volume
  --volume-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--volume-arn`` (string)


  The Amazon Resource Name (ARN) of the volume. Use the  list-volumes operation to return a list of gateway volumes.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

VolumeARN -> (string)

  

  The Amazon Resource Name (ARN) of the storage volume that was deleted. It is the same ARN you provided in the request.

  

  

