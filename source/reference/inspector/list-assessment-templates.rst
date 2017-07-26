[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector list-assessment-templates:


*************************
list-assessment-templates
*************************



===========
Description
===========



Lists the assessment templates that correspond to the assessment targets that are specified by the ARNs of the assessment targets.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/ListAssessmentTemplates>`_


========
Synopsis
========

::

    list-assessment-templates
  [--assessment-target-arns <value>]
  [--filter <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--assessment-target-arns`` (list)


  A list of ARNs that specifies the assessment targets whose assessment templates you want to list.

  



Syntax::

  "string" "string" ...



``--filter`` (structure)


  You can use this parameter to specify a subset of data to be included in the action's response.

   

  For a record to match a filter, all specified filter attributes must match. When multiple values are specified for a filter attribute, any of the values can match.

  



Shorthand Syntax::

    namePattern=string,durationRange={minSeconds=integer,maxSeconds=integer},rulesPackageArns=string,string




JSON Syntax::

  {
    "namePattern": "string",
    "durationRange": {
      "minSeconds": integer,
      "maxSeconds": integer
    },
    "rulesPackageArns": ["string", ...]
  }



``--next-token`` (string)


  You can use this parameter when paginating results. Set the value of this parameter to null on your first call to the **list-assessment-templates** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from the previous response to continue listing data.

  

``--max-results`` (integer)


  You can use this parameter to indicate the maximum number of items you want in the response. The default value is 10. The maximum value is 500.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list assessment templates**

The following ``list-assessment-templates`` command lists all existing assessment templates::

  aws inspector list-assessment-templates

Output::

   {
	  "assessmentTemplateArns": [
	  "arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-4r1V2mAw",
	  "arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-Uza6ihLh"
	  ]
   }

For more information, see `Amazon Inspector Assessment Templates and Assessment Runs`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Assessment Templates and Assessment Runs`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_assessments.html



======
Output
======

assessmentTemplateArns -> (list)

  

  A list of ARNs that specifies the assessment templates returned by the action.

  

  (string)

    

    

  

nextToken -> (string)

  

  When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to null.

  

  

