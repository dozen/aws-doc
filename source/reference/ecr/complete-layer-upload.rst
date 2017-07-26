[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr complete-layer-upload:


*********************
complete-layer-upload
*********************



===========
Description
===========



Inform Amazon ECR that the image layer upload for a specified registry, repository name, and upload ID, has completed. You can optionally provide a ``sha256`` digest of the image layer for data validation purposes.

 

.. note::

   

  This operation is used by the Amazon ECR proxy, and it is not intended for general use by customers. Use the ``docker`` CLI to pull, tag, and push images.

   



========
Synopsis
========

::

    complete-layer-upload
  [--registry-id <value>]
  --repository-name <value>
  --upload-id <value>
  --layer-digests <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry to which to upload layers. If you do not specify a registry, the default registry is assumed.

  

``--repository-name`` (string)


  The name of the repository to associate with the image layer.

  

``--upload-id`` (string)


  The upload ID from a previous  initiate-layer-upload operation to associate with the image layer.

  

``--layer-digests`` (list)


  The ``sha256`` digest of the image layer.

  



Syntax::

  "string" "string" ...



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

  

  The upload ID associated with the layer.

  

  

layerDigest -> (string)

  

  The ``sha256`` digest of the image layer.

  

  

