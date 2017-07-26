[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway create-cached-iscsi-volume:


**************************
create-cached-iscsi-volume
**************************



===========
Description
===========



This operation creates a cached volume on a specified cached gateway. This operation is supported only for the gateway-cached volume architecture.

 

.. note::

  Cache storage must be allocated to the gateway before you can create a cached volume. Use the  add-cache operation to add cache storage to a gateway. 

 

In the request, you must specify the gateway, size of the volume in bytes, the iSCSI target name, an IP address on which to expose the target, and a unique client token. In response, AWS Storage Gateway creates the volume and returns information about it such as the volume Amazon Resource Name (ARN), its size, and the iSCSI target ARN that initiators can use to connect to the volume target.



========
Synopsis
========

::

    create-cached-iscsi-volume
  --gateway-arn <value>
  --volume-size-in-bytes <value>
  [--snapshot-id <value>]
  --target-name <value>
  --network-interface-id <value>
  --client-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--volume-size-in-bytes`` (long)


``--snapshot-id`` (string)


``--target-name`` (string)


``--network-interface-id`` (string)


``--client-token`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

VolumeARN -> (string)

  

  

TargetARN -> (string)

  

  

