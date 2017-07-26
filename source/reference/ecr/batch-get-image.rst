[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr batch-get-image:


***************
batch-get-image
***************



===========
Description
===========



Gets detailed information for specified images within a specified repository. Images are specified with either ``imageTag`` or ``imageDigest`` .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecr-2015-09-21/BatchGetImage>`_


========
Synopsis
========

::

    batch-get-image
  [--registry-id <value>]
  --repository-name <value>
  --image-ids <value>
  [--accepted-media-types <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry that contains the images to describe. If you do not specify a registry, the default registry is assumed.

  

``--repository-name`` (string)


  The repository that contains the images to describe.

  

``--image-ids`` (list)


  A list of image ID references that correspond to images to describe. The format of the ``imageIds`` reference is ``imageTag=tag`` or ``imageDigest=digest`` .

  



Shorthand Syntax::

    imageDigest=string,imageTag=string ...




JSON Syntax::

  [
    {
      "imageDigest": "string",
      "imageTag": "string"
    }
    ...
  ]



``--accepted-media-types`` (list)


  The accepted media types for the request.

   

  Valid values: ``application/vnd.docker.distribution.manifest.v1+json`` | ``application/vnd.docker.distribution.manifest.v2+json`` | ``application/vnd.oci.image.manifest.v1+json``  

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe an image**

This example describes an image with the tag ``precise`` in a repository called
``ubuntu`` in the default registry for an account.

Command::

  aws ecr batch-get-image --repository-name ubuntu --image-ids imageTag=precise


======
Output
======

images -> (list)

  

  A list of image objects corresponding to the image references in the request.

  

  (structure)

    

    An object representing an Amazon ECR image.

    

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

      

      

    

  

failures -> (list)

  

  Any failures associated with the call.

  

  (structure)

    

    An object representing an Amazon ECR image failure.

    

    imageId -> (structure)

      

      The image ID associated with the failure.

      

      imageDigest -> (string)

        

        The ``sha256`` digest of the image manifest.

        

        

      imageTag -> (string)

        

        The tag used for the image.

        

        

      

    failureCode -> (string)

      

      The code associated with the failure.

      

      

    failureReason -> (string)

      

      The reason for the failure.

      

      

    

  

