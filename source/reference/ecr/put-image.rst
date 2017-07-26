[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr put-image:


*********
put-image
*********



===========
Description
===========



Creates or updates the image manifest associated with an image.

 

.. note::

   

  This operation is used by the Amazon ECR proxy, and it is not intended for general use by customers. Use the ``docker`` CLI to pull, tag, and push images.

   



========
Synopsis
========

::

    put-image
  [--registry-id <value>]
  --repository-name <value>
  --image-manifest <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry that contains the repository in which to put the image. If you do not specify a registry, the default registry is assumed.

  

``--repository-name`` (string)


  The name of the repository in which to put the image.

  

``--image-manifest`` (string)


  The image manifest corresponding to the image to be uploaded.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

image -> (structure)

  

  Details of the image uploaded.

  

  registryId -> (string)

    

    The AWS account ID associated with the registry containing the image.

    

    

  repositoryName -> (string)

    

    The name of the repository associated with the image.

    

    

  imageId -> (structure)

    

    An object containing the image tag and image digest associated with an image.

    

    imageDigest -> (string)

      

      The ``sha256`` digest of the image manifest.

      

      

    imageTag -> (string)

      

      The tag used for the image.

      

      

    

  imageManifest -> (string)

    

    The image manifest associated with the image.

    

    

  

