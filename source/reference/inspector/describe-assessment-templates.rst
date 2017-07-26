[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector describe-assessment-templates:


*****************************
describe-assessment-templates
*****************************



===========
Description
===========



Describes the assessment templates that are specified by the ARNs of the assessment templates.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/DescribeAssessmentTemplates>`_


========
Synopsis
========

::

    describe-assessment-templates
  --assessment-template-arns <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--assessment-template-arns`` (list)




Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe assessment templates**

The following ``describe-assessment-templates`` command describes the assessment template with the ARN of ``arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-4r1V2mAw``::

  aws inspector describe-assessment-templates --assessment-template-arns arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-4r1V2mAw

Output::

   {
	 "assessmentTemplates": [
	   {
		 "arn": "arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-4r1V2mAw",
		 "assessmentTargetArn": "arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq",
		 "createdAt": 1458074191.844,
		 "durationInSeconds": 3600,
		 "name": "ExampleAssessmentTemplate",
		 "rulesPackageArns": [
		   "arn:aws:inspector:us-west-2:758058086616:rulespackage/0-X1KXtawP"
		 ],
		 "userAttributesForFindings": []
	   }
	 ],
	 "failedItems": {}
   } 

For more information, see `Amazon Inspector Assessment Templates and Assessment Runs`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Assessment Templates and Assessment Runs`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_assessments.html



======
Output
======

assessmentTemplates -> (list)

  

  Information about the assessment templates.

  

  (structure)

    

    Contains information about an Amazon Inspector assessment template. This data type is used as the response element in the  describe-assessment-templates action.

    

    arn -> (string)

      

      The ARN of the assessment template.

      

      

    name -> (string)

      

      The name of the assessment template.

      

      

    assessmentTargetArn -> (string)

      

      The ARN of the assessment target that corresponds to this assessment template.

      

      

    durationInSeconds -> (integer)

      

      The duration in seconds specified for this assessment tempate. The default value is 3600 seconds (one hour). The maximum value is 86400 seconds (one day).

      

      

    rulesPackageArns -> (list)

      

      The rules packages that are specified for this assessment template.

      

      (string)

        

        

      

    userAttributesForFindings -> (list)

      

      The user-defined attributes that are assigned to every generated finding from the assessment run that uses this assessment template.

      

      (structure)

        

        This data type is used as a request parameter in the  add-attributes-to-findings and  create-assessment-template actions.

        

        key -> (string)

          

          The attribute key.

          

          

        value -> (string)

          

          The value assigned to the attribute key.

          

          

        

      

    createdAt -> (timestamp)

      

      The time at which the assessment template is created.

      

      

    

  

failedItems -> (map)

  

  Assessment template details that cannot be described. An error code is provided for each failed item.

  

  key -> (string)

    

    

  value -> (structure)

    

    Includes details about the failed items.

    

    failureCode -> (string)

      

      The status code of a failed item.

      

      

    retryable -> (boolean)

      

      Indicates whether you can immediately retry a request for this item for a specified resource.

      

      

    

  

