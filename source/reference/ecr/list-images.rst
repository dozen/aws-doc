[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr list-images:


***********
list-images
***********



===========
Description
===========



Lists all the image IDs for a given repository.



========
Synopsis
========

::

    list-images
  [--registry-id <value>]
  --repository-name <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry that contains the repository to list images in. If you do not specify a registry, the default registry is assumed.

  

``--repository-name`` (string)


  The repository whose image IDs are to be listed.

  

``--next-token`` (string)


  The ``nextToken`` value returned from a previous paginated ``list-images`` request where ``maxResults`` was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the ``nextToken`` value. This value is ``null`` when there are no more results to return.

  

``--max-results`` (integer)


  The maximum number of image results returned by ``list-images`` in paginated output. When this parameter is used, ``list-images`` only returns ``maxResults`` results in a single page along with a ``nextToken`` response element. The remaining results of the initial request can be seen by sending another ``list-images`` request with the returned ``nextToken`` value. This value can be between 1 and 100. If this parameter is not used, then ``list-images`` returns up to 100 results and a ``nextToken`` value, if applicable.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

imageIds -> (list)

  

  The list of image IDs for the requested repository.

  

  (structure)

    

    imageDigest -> (string)

      

      The ``sha256`` digest of the image manifest.

      

      

    imageTag -> (string)

      

      The tag used for the image.

      

      

    

  

nextToken -> (string)

  

  The ``nextToken`` value to include in a future ``list-images`` request. When the results of a ``list-images`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

