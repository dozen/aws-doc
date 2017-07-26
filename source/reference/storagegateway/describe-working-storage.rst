[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway describe-working-storage:


************************
describe-working-storage
************************



===========
Description
===========



This operation returns information about the working storage of a gateway. This operation is supported only for the gateway-stored volume architecture. This operation is deprecated in cached-volumes API version (20120630). Use describe-upload-buffer instead.

 

.. note::

  

  Working storage is also referred to as upload buffer. You can also use the describe-upload-buffer operation to add upload buffer to a stored-volume gateway.

  

 

The response includes disk IDs that are configured as working storage, and it includes the amount of working storage allocated and used.



========
Synopsis
========

::

    describe-working-storage
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

  

  

DiskIds -> (list)

  

  An array of the gateway's local disk IDs that are configured as working storage. Each local disk ID is specified as a string (minimum length of 1 and maximum length of 300). If no local disks are configured as working storage, then the DiskIds array is empty.

  

  (string)

    

    

  

WorkingStorageUsedInBytes -> (long)

  

  The total working storage in bytes in use by the gateway. If no working storage is configured for the gateway, this field returns 0.

  

  

WorkingStorageAllocatedInBytes -> (long)

  

  The total working storage in bytes allocated for the gateway. If no working storage is configured for the gateway, this field returns 0.

  

  

