[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr batch-delete-image:


******************
batch-delete-image
******************



===========
Description
===========



Deletes a list of specified images within a specified repository. Images are specified with either ``imageTag`` or ``imageDigest`` .

 

You can remove a tag from an image by specifying the image's tag in your request. When you remove the last tag from an image, the image is deleted from your repository.

 

You can completely delete an image (and all of its tags) by specifying the image's digest in your request.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecr-2015-09-21/BatchDeleteImage>`_


========
Synopsis
========

::

    batch-delete-image
  [--registry-id <value>]
  --repository-name <value>
  --image-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry that contains the image to delete. If you do not specify a registry, the default registry is assumed.

  

``--repository-name`` (string)


  The repository that contains the image to delete.

  

``--image-ids`` (list)


  A list of image ID references that correspond to images to delete. The format of the ``imageIds`` reference is ``imageTag=tag`` or ``imageDigest=digest`` .

  



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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete an image**

This example deletes an image with the tag ``precise`` in a repository called
``ubuntu`` in the default registry for an account.

Command::

  aws ecr batch-delete-image --repository-name ubuntu --image-ids imageTag=precise

Output::

  {
      "failures": [],
      "imageIds": [
          {
              "imageTag": "precise",
              "imageDigest": "sha256:19665f1e6d1e504117a1743c0a3d3753086354a38375961f2e665416ef4b1b2f"
          }
      ]
  }


======
Output
======

imageIds -> (list)

  

  The image IDs of the deleted images.

  

  (structure)

    

    An object with identifying information for an Amazon ECR image.

    

    imageDigest -> (string)

      

      The ``sha256`` digest of the image manifest.

      

      

    imageTag -> (string)

      

      The tag used for the image.

      

      

    

  

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

      

      

    

  

