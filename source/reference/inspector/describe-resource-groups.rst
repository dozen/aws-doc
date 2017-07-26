[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector describe-resource-groups:


************************
describe-resource-groups
************************



===========
Description
===========



Describes the resource groups that are specified by the ARNs of the resource groups.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/DescribeResourceGroups>`_


========
Synopsis
========

::

    describe-resource-groups
  --resource-group-arns <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-group-arns`` (list)


  The ARN that specifies the resource group that you want to describe.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe resource groups**

The following ``describe-resource-groups`` command describes the resource group with the ARN of ``arn:aws:inspector:us-west-2:123456789012:resourcegroup/0-PyGXopAI``::

  aws inspector describe-resource-groups --resource-group-arns arn:aws:inspector:us-west-2:123456789012:resourcegroup/0-PyGXopAI

Output::

   {
	 "failedItems": {},
	 "resourceGroups": [
	   {
		 "arn": "arn:aws:inspector:us-west-2:123456789012:resourcegroup/0-PyGXopAI",
		 "createdAt": 1458074191.098,
		 "tags": [
		   {
			 "key": "Name",
			 "value": "example"
		   }
		 ]
	   }
	 ]
   }  

For more information, see `Amazon Inspector Assessment Targets`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Assessment Targets`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_applications.html



======
Output
======

resourceGroups -> (list)

  

  Information about a resource group.

  

  (structure)

    

    Contains information about a resource group. The resource group defines a set of tags that, when queried, identify the AWS resources that make up the assessment target. This data type is used as the response element in the  describe-resource-groups action.

    

    arn -> (string)

      

      The ARN of the resource group.

      

      

    tags -> (list)

      

      The tags (key and value pairs) of the resource group. This data type property is used in the  create-resource-group action.

      

      (structure)

        

        This data type is used as one of the elements of the  ResourceGroup data type.

        

        key -> (string)

          

          A tag key.

          

          

        value -> (string)

          

          The value assigned to a tag key.

          

          

        

      

    createdAt -> (timestamp)

      

      The time at which resource group is created.

      

      

    

  

failedItems -> (map)

  

  Resource group details that cannot be described. An error code is provided for each failed item.

  

  key -> (string)

    

    

  value -> (structure)

    

    Includes details about the failed items.

    

    failureCode -> (string)

      

      The status code of a failed item.

      

      

    retryable -> (boolean)

      

      Indicates whether you can immediately retry a request for this item for a specified resource.

      

      

    

  

