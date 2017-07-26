[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr get-download-url-for-layer:


**************************
get-download-url-for-layer
**************************



===========
Description
===========



Retrieves the pre-signed Amazon S3 download URL corresponding to an image layer. You can only get URLs for image layers that are referenced in an image.

 

.. note::

   

  This operation is used by the Amazon ECR proxy, and it is not intended for general use by customers. Use the ``docker`` CLI to pull, tag, and push images.

   



========
Synopsis
========

::

    get-download-url-for-layer
  [--registry-id <value>]
  --repository-name <value>
  --layer-digest <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry that contains the image layer to download. If you do not specify a registry, the default registry is assumed.

  

``--repository-name`` (string)


  The name of the repository that is associated with the image layer to download.

  

``--layer-digest`` (string)


  The digest of the image layer to download.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

downloadUrl -> (string)

  

  The pre-signed Amazon S3 download URL for the requested layer.

  

  

layerDigest -> (string)

  

  The digest of the image layer to download.

  

  

