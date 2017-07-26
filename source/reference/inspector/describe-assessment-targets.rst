[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector describe-assessment-targets:


***************************
describe-assessment-targets
***************************



===========
Description
===========



Describes the assessment targets that are specified by the ARNs of the assessment targets.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/DescribeAssessmentTargets>`_


========
Synopsis
========

::

    describe-assessment-targets
  --assessment-target-arns <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--assessment-target-arns`` (list)


  The ARNs that specifies the assessment targets that you want to describe.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe assessment targets**

The following ``describe-assessment-targets`` command describes the assessment target with the ARN of ``arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq``::

  aws inspector describe-assessment-targets --assessment-target-arns arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq

Output::

   {
	 "assessmentTargets": [
	   {
		 "arn": "arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq",
		 "createdAt": 1458074191.459,
		 "name": "ExampleAssessmentTarget",
		 "resourceGroupArn": "arn:aws:inspector:us-west-2:123456789012:resourcegroup/0-PyGXopAI",
		 "updatedAt": 1458074191.459
	   }
	 ],
	 "failedItems": {}
   }  

For more information, see `Amazon Inspector Assessment Targets`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Assessment Targets`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_applications.html



======
Output
======

assessmentTargets -> (list)

  

  Information about the assessment targets.

  

  (structure)

    

    Contains information about an Amazon Inspector application. This data type is used as the response element in the  describe-assessment-targets action.

    

    arn -> (string)

      

      The ARN that specifies the Amazon Inspector assessment target.

      

      

    name -> (string)

      

      The name of the Amazon Inspector assessment target.

      

      

    resourceGroupArn -> (string)

      

      The ARN that specifies the resource group that is associated with the assessment target.

      

      

    createdAt -> (timestamp)

      

      The time at which the assessment target is created.

      

      

    updatedAt -> (timestamp)

      

      The time at which  update-assessment-target is called.

      

      

    

  

failedItems -> (map)

  

  Assessment target details that cannot be described. An error code is provided for each failed item.

  

  key -> (string)

    

    

  value -> (structure)

    

    Includes details about the failed items.

    

    failureCode -> (string)

      

      The status code of a failed item.

      

      

    retryable -> (boolean)

      

      Indicates whether you can immediately retry a request for this item for a specified resource.

      

      

    

  

