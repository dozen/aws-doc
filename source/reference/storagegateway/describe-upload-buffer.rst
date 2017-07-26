[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway describe-upload-buffer:


**********************
describe-upload-buffer
**********************



===========
Description
===========



Returns information about the upload buffer of a gateway. This operation is supported for the stored volume, cached volume and tape gateway architectures.

 

The response includes disk IDs that are configured as upload buffer space, and it includes the amount of upload buffer space allocated and used.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/DescribeUploadBuffer>`_


========
Synopsis
========

::

    describe-upload-buffer
  --gateway-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

GatewayARN -> (string)

  

  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

  

DiskIds -> (list)

  

  (string)

    

    

  

UploadBufferUsedInBytes -> (long)

  

  

UploadBufferAllocatedInBytes -> (long)

  

  

