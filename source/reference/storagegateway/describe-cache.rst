[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway describe-cache:


**************
describe-cache
**************



===========
Description
===========



This operation returns information about the cache of a gateway. This operation is supported only for the gateway-cached volume architecture. 

 

The response includes disk IDs that are configured as cache, and it includes the amount of cache allocated and used. 



========
Synopsis
========

::

    describe-cache
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

  

  (string)

    

    

  

CacheAllocatedInBytes -> (long)

  

  

CacheUsedPercentage -> (double)

  

  

CacheDirtyPercentage -> (double)

  

  

CacheHitPercentage -> (double)

  

  

CacheMissPercentage -> (double)

  

  

