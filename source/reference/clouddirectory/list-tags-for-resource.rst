[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory list-tags-for-resource:


**********************
list-tags-for-resource
**********************



===========
Description
===========



Returns tags for a resource. Tagging is currently supported only for directories with a limit of 50 tags per directory. All 50 tags are returned for a given directory with this API call.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/ListTagsForResource>`_


========
Synopsis
========

::

    list-tags-for-resource
  --resource-arn <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn`` (string)


  The Amazon Resource Name (ARN) of the resource. Tagging is only supported for directories.

  

``--next-token`` (string)


  The pagination token. This is for future use. Currently pagination is not supported for tagging.

  

``--max-results`` (integer)


  The ``MaxResults`` parameter sets the maximum number of results returned in a single page. This is for future use and is not supported currently.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Tags -> (list)

  

  A list of tag key value pairs that are associated with the response.

  

  (structure)

    

    The tag structure that contains a tag key and value.

    

    Key -> (string)

      

      The key that is associated with the tag.

      

      

    Value -> (string)

      

      The value that is associated with the tag.

      

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is null when there are no more results to return.

  

  

