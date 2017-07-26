[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr batch-get-image:


***************
batch-get-image
***************



===========
Description
===========



Gets detailed information for specified images within a specified repository. Images are specified with either ``imageTag`` or ``imageDigest`` .



========
Synopsis
========

::

    batch-get-image
  [--registry-id <value>]
  --repository-name <value>
  --image-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

    

    Object representing an image.

    

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

      

      

    

  

