[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway create-stored-iscsi-volume:


**************************
create-stored-iscsi-volume
**************************



===========
Description
===========



Creates a volume on a specified gateway. This operation is only supported in the stored volume gateway architecture.

 

The size of the volume to create is inferred from the disk size. You can choose to preserve existing data on the disk, create volume from an existing snapshot, or create an empty volume. If you choose to create an empty gateway volume, then any existing data on the disk is erased.

 

In the request you must specify the gateway and the disk information on which you are creating the volume. In response, the gateway creates the volume and returns volume information such as the volume Amazon Resource Name (ARN), its size, and the iSCSI target ARN that initiators can use to connect to the volume target.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/CreateStorediSCSIVolume>`_


========
Synopsis
========

::

    create-stored-iscsi-volume
  --gateway-arn <value>
  --disk-id <value>
  [--snapshot-id <value>]
  --preserve-existing-data | --no-preserve-existing-data
  --target-name <value>
  --network-interface-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--disk-id`` (string)


  The unique identifier for the gateway local disk that is configured as a stored volume. Use `list-local-disks <http://docs.aws.amazon.com/storagegateway/latest/userguide/API_ListLocalDisks.html>`_ to list disk IDs for a gateway.

  

``--snapshot-id`` (string)


  The snapshot ID (e.g. "snap-1122aabb") of the snapshot to restore as the new stored volume. Specify this field if you want to create the iSCSI storage volume from a snapshot otherwise do not include this field. To list snapshots for your account use `DescribeSnapshots <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/ApiReference-query-DescribeSnapshots.html>`_ in the *Amazon Elastic Compute Cloud API Reference* .

  

``--preserve-existing-data`` | ``--no-preserve-existing-data`` (boolean)


  Specify this field as true if you want to preserve the data on the local disk. Otherwise, specifying this field as false creates an empty volume.

   

  Valid Values: true, false

  

``--target-name`` (string)


  The name of the iSCSI target used by initiators to connect to the target and as a suffix for the target ARN. For example, specifying ``target-name`` as *myvolume* results in the target ARN of arn:aws:storagegateway:us-east-1:111122223333:gateway/sgw-12A3456B/target/iqn.1997-05.com.amazon:myvolume. The target name must be unique across all volumes of a gateway.

  

``--network-interface-id`` (string)


  The network interface of the gateway on which to expose the iSCSI target. Only IPv4 addresses are accepted. Use  describe-gateway-information to get a list of the network interfaces available on a gateway.

   

  Valid Values: A valid IP address.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

VolumeARN -> (string)

  

  The Amazon Resource Name (ARN) of the configured volume.

  

  

VolumeSizeInBytes -> (long)

  

  The size of the volume in bytes.

  

  

TargetARN -> (string)

  

  he Amazon Resource Name (ARN) of the volume target that includes the iSCSI name that initiators can use to connect to the target.

  

  

