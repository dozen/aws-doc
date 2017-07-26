[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr describe-images:


***************
describe-images
***************



===========
Description
===========



Returns metadata about the images in a repository, including image size, image tags, and creation date.

 

.. note::

   

  Beginning with Docker version 1.9, the Docker client compresses image layers before pushing them to a V2 Docker registry. The output of the ``docker images`` command shows the uncompressed image size, so it may return a larger image size than the image sizes returned by  describe-images .

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecr-2015-09-21/DescribeImages>`_


``describe-images`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``imageDetails``


========
Synopsis
========

::

    describe-images
  [--registry-id <value>]
  --repository-name <value>
  [--image-ids <value>]
  [--filter <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry that contains the repository in which to describe images. If you do not specify a registry, the default registry is assumed.

  

``--repository-name`` (string)


  A list of repositories to describe. If this parameter is omitted, then all repositories in a registry are described.

  

``--image-ids`` (list)


  The list of image IDs for the requested repository.

  



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



``--filter`` (structure)


  The filter key and value with which to filter your ``describe-images`` results.

  



Shorthand Syntax::

    tagStatus=string




JSON Syntax::

  {
    "tagStatus": "TAGGED"|"UNTAGGED"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

imageDetails -> (list)

  

  A list of  ImageDetail objects that contain data about the image.

  

  (structure)

    

    An object that describes an image returned by a  describe-images operation.

    

    registryId -> (string)

      

      The AWS account ID associated with the registry to which this image belongs.

      

      

    repositoryName -> (string)

      

      The name of the repository to which this image belongs.

      

      

    imageDigest -> (string)

      

      The ``sha256`` digest of the image manifest.

      

      

    imageTags -> (list)

      

      The list of tags associated with this image.

      

      (string)

        

        

      

    imageSizeInBytes -> (long)

      

      The size, in bytes, of the image in the repository.

       

      .. note::

         

        Beginning with Docker version 1.9, the Docker client compresses image layers before pushing them to a V2 Docker registry. The output of the ``docker images`` command shows the uncompressed image size, so it may return a larger image size than the image sizes returned by  describe-images .

         

      

      

    imagePushedAt -> (timestamp)

      

      The date and time, expressed in standard JavaScript date format, at which the current image was pushed to the repository. 

      

      

    

  

nextToken -> (string)

  

  The ``nextToken`` value to include in a future ``describe-images`` request. When the results of a ``describe-images`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

