[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway list-volume-recovery-points:


***************************
list-volume-recovery-points
***************************



===========
Description
===========



This operation lists the recovery points for a specified gateway. This operation is supported only for the gateway-cached volume architecture.

 

Each gateway-cached volume has one recovery point. A volume recovery point is a point in time at which all data of the volume is consistent and from which you can create a snapshot. To create a snapshot from a volume recovery point use the  create-snapshot-from-volume-recovery-point operation.



========
Synopsis
========

::

    list-volume-recovery-points
  --gateway-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

GatewayARN -> (string)

  

  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

  

VolumeRecoveryPointInfos -> (list)

  

  (structure)

    

    VolumeARN -> (string)

      

      

    VolumeSizeInBytes -> (long)

      

      

    VolumeUsageInBytes -> (long)

      

      

    VolumeRecoveryPointTime -> (string)

      

      

    

  

