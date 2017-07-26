[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb untag-resource:


**************
untag-resource
**************



===========
Description
===========



Removes the association of tags from an Amazon DynamoDB resource. You can call untag-resource up to 5 times per second, per account. 

 

For an overview on tagging DynamoDB resources, see `Tagging for DynamoDB <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Tagging.html>`_ in the *Amazon DynamoDB Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dynamodb-2012-08-10/UntagResource>`_


========
Synopsis
========

::

    untag-resource
  --resource-arn <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn`` (string)


  The Amazon DyanamoDB resource the tags will be removed from. This value is an Amazon Resource Name (ARN).

  

``--tag-keys`` (list)


  A list of tag keys. Existing tags of the resource whose keys are members of this list will be removed from the Amazon DynamoDB resource.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None