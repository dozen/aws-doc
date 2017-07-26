[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway describe-upload-buffer:


**********************
describe-upload-buffer
**********************



===========
Description
===========



This operation returns information about the upload buffer of a gateway. This operation is supported for both the gateway-stored and gateway-cached volume architectures. 

 

The response includes disk IDs that are configured as upload buffer space, and it includes the amount of upload buffer space allocated and used.



========
Synopsis
========

::

    describe-upload-buffer
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

    

    

  

UploadBufferUsedInBytes -> (long)

  

  

UploadBufferAllocatedInBytes -> (long)

  

  

