[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks list-tags:


*********
list-tags
*********



===========
Description
===========



Returns a list of tags that are applied to the specified stack or layer.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/ListTags>`_


========
Synopsis
========

::

    list-tags
  --resource-arn <value>
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn`` (string)


  The stack or layer's Amazon Resource Number (ARN).

  

``--max-results`` (integer)


  Do not use. A validation exception occurs if you add a ``max-results`` parameter to a ``ListTagsRequest`` call. 

  

``--next-token`` (string)


  Do not use. A validation exception occurs if you add a ``next-token`` parameter to a ``ListTagsRequest`` call. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Tags -> (map)

  

  A set of key-value pairs that contain tag keys and tag values that are attached to a stack or layer.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

NextToken -> (string)

  

  If a paginated request does not return all of the remaining results, this parameter is set to a token that you can assign to the request object's ``next-token`` parameter to get the next set of results. If the previous paginated request returned all of the remaining results, this parameter is set to ``null`` . 

  

  

