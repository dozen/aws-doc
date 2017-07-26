[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb tag-resource:


************
tag-resource
************



===========
Description
===========



Associate a set of tags with an Amazon DynamoDB resource. You can then activate these user-defined tags so that they appear on the Billing and Cost Management console for cost allocation tracking. You can call tag-resource up to 5 times per second, per account. 

 

For an overview on tagging DynamoDB resources, see `Tagging for DynamoDB <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Tagging.html>`_ in the *Amazon DynamoDB Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dynamodb-2012-08-10/TagResource>`_


========
Synopsis
========

::

    tag-resource
  --resource-arn <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn`` (string)


  Identifies the Amazon DynamoDB resource to which tags should be added. This value is an Amazon Resource Name (ARN).

  

``--tags`` (list)


  The tags to be assigned to the Amazon DynamoDB resource.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None