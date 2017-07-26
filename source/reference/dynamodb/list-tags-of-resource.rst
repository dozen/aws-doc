[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb list-tags-of-resource:


*********************
list-tags-of-resource
*********************



===========
Description
===========



List all tags on an Amazon DynamoDB resource. You can call list-tags-of-resource up to 10 times per second, per account.

 

For an overview on tagging DynamoDB resources, see `Tagging for DynamoDB <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Tagging.html>`_ in the *Amazon DynamoDB Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dynamodb-2012-08-10/ListTagsOfResource>`_


========
Synopsis
========

::

    list-tags-of-resource
  --resource-arn <value>
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn`` (string)


  The Amazon DynamoDB resource with tags to be listed. This value is an Amazon Resource Name (ARN).

  

``--next-token`` (string)


  An optional string that, if supplied, must be copied from the output of a previous call to ListTagOfResource. When provided in this manner, this API fetches the next page of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Tags -> (list)

  

  The tags currently associated with the Amazon DynamoDB resource.

  

  (structure)

    

    Describes a tag. A tag is a key-value pair. You can add up to 50 tags to a single DynamoDB table. 

     

    AWS-assigned tag names and values are automatically assigned the aws: prefix, which the user cannot assign. AWS-assigned tag names do not count towards the tag limit of 50. User-assigned tag names have the prefix user: in the Cost Allocation Report. You cannot backdate the application of a tag. 

     

    For an overview on tagging DynamoDB resources, see `Tagging for DynamoDB <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Tagging.html>`_ in the *Amazon DynamoDB Developer Guide* .

    

    Key -> (string)

      

      The key of the tag.Tag keys are case sensitive. Each DynamoDB table can only have up to one tag with the same key. If you try to add an existing tag (same key), the existing tag value will be updated to the new value. 

      

      

    Value -> (string)

      

      The value of the tag. Tag values are case-sensitive and can be null.

      

      

    

  

NextToken -> (string)

  

  If this value is returned, there are additional results to be displayed. To retrieve them, call list-tags-of-resource again, with NextToken set to this value.

  

  

