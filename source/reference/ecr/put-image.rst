[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr put-image:


*********
put-image
*********



===========
Description
===========



Creates or updates the image manifest and tags associated with an image.

 

.. note::

   

  This operation is used by the Amazon ECR proxy, and it is not intended for general use by customers for pulling and pushing images. In most cases, you should use the ``docker`` CLI to pull, tag, and push images.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecr-2015-09-21/PutImage>`_


========
Synopsis
========

::

    put-image
  [--registry-id <value>]
  --repository-name <value>
  --image-manifest <value>
  [--image-tag <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry that contains the repository in which to put the image. If you do not specify a registry, the default registry is assumed.

  

``--repository-name`` (string)


  The name of the repository in which to put the image.

  

``--image-manifest`` (string)


  The image manifest corresponding to the image to be uploaded.

  

``--image-tag`` (string)


  The tag to associate with the image. This parameter is required for images that use the Docker Image Manifest V2 Schema 2 or OCI formats.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    

  

