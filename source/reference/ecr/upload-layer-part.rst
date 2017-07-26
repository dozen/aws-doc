[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr upload-layer-part:


*****************
upload-layer-part
*****************



===========
Description
===========



Uploads an image layer part to Amazon ECR.

 

.. note::

   

  This operation is used by the Amazon ECR proxy, and it is not intended for general use by customers. Use the ``docker`` CLI to pull, tag, and push images.

   



========
Synopsis
========

::

    upload-layer-part
  [--registry-id <value>]
  --repository-name <value>
  --upload-id <value>
  --part-first-byte <value>
  --part-last-byte <value>
  --layer-part-blob <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry that you are uploading layer parts to. If you do not specify a registry, the default registry is assumed.

  

``--repository-name`` (string)


  The name of the repository that you are uploading layer parts to.

  

``--upload-id`` (string)


  The upload ID from a previous  initiate-layer-upload operation to associate with the layer part upload.

  

``--part-first-byte`` (long)


  The integer value of the first byte of the layer part.

  

``--part-last-byte`` (long)


  The integer value of the last byte of the layer part.

  

``--layer-part-blob`` (blob)


  The base64-encoded layer part payload.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

registryId -> (string)

  

  The registry ID associated with the request.

  

  

repositoryName -> (string)

  

  The repository name associated with the request.

  

  

uploadId -> (string)

  

  The upload ID associated with the request.

  

  

lastByteReceived -> (long)

  

  The integer value of the last byte received in the request.

  

  

