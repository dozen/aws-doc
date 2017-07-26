[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway create-cached-iscsi-volume:


**************************
create-cached-iscsi-volume
**************************



===========
Description
===========



Creates a cached volume on a specified cached volume gateway. This operation is only supported in the cached volume gateway architecture.

 

.. note::

   

  Cache storage must be allocated to the gateway before you can create a cached volume. Use the  add-cache operation to add cache storage to a gateway. 

   

 

In the request, you must specify the gateway, size of the volume in bytes, the iSCSI target name, an IP address on which to expose the target, and a unique client token. In response, the gateway creates the volume and returns information about it. This information includes the volume Amazon Resource Name (ARN), its size, and the iSCSI target ARN that initiators can use to connect to the volume target.

 

Optionally, you can provide the ARN for an existing volume as the ``SourceVolumeARN`` for this cached volume, which creates an exact copy of the existing volume’s latest recovery point. The ``VolumeSizeInBytes`` value must be equal to or larger than the size of the copied volume, in bytes.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/CreateCachediSCSIVolume>`_


========
Synopsis
========

::

    create-cached-iscsi-volume
  --gateway-arn <value>
  --volume-size-in-bytes <value>
  [--snapshot-id <value>]
  --target-name <value>
  [--source-volume-arn <value>]
  --network-interface-id <value>
  --client-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--volume-size-in-bytes`` (long)


``--snapshot-id`` (string)


``--target-name`` (string)


``--source-volume-arn`` (string)


  The ARN for an existing volume. Specifying this ARN makes the new volume into an exact copy of the specified existing volume's latest recovery point. The ``VolumeSizeInBytes`` value for this new volume must be equal to or larger than the size of the existing volume, in bytes.

  

``--network-interface-id`` (string)


``--client-token`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

VolumeARN -> (string)

  

  

TargetARN -> (string)

  

  

