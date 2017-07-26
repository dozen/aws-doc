[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector list-assessment-runs:


********************
list-assessment-runs
********************



===========
Description
===========



Lists the assessment runs that correspond to the assessment templates that are specified by the ARNs of the assessment templates.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/ListAssessmentRuns>`_


========
Synopsis
========

::

    list-assessment-runs
  [--assessment-template-arns <value>]
  [--filter <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--assessment-template-arns`` (list)


  The ARNs that specify the assessment templates whose assessment runs you want to list.

  



Syntax::

  "string" "string" ...



``--filter`` (structure)


  You can use this parameter to specify a subset of data to be included in the action's response.

   

  For a record to match a filter, all specified filter attributes must match. When multiple values are specified for a filter attribute, any of the values can match.

  



Shorthand Syntax::

    namePattern=string,states=string,string,durationRange={minSeconds=integer,maxSeconds=integer},rulesPackageArns=string,string,startTimeRange={beginDate=timestamp,endDate=timestamp},completionTimeRange={beginDate=timestamp,endDate=timestamp},stateChangeTimeRange={beginDate=timestamp,endDate=timestamp}




JSON Syntax::

  {
    "namePattern": "string",
    "states": ["CREATED"|"START_DATA_COLLECTION_PENDING"|"START_DATA_COLLECTION_IN_PROGRESS"|"COLLECTING_DATA"|"STOP_DATA_COLLECTION_PENDING"|"DATA_COLLECTED"|"START_EVALUATING_RULES_PENDING"|"EVALUATING_RULES"|"FAILED"|"ERROR"|"COMPLETED"|"COMPLETED_WITH_ERRORS", ...],
    "durationRange": {
      "minSeconds": integer,
      "maxSeconds": integer
    },
    "rulesPackageArns": ["string", ...],
    "startTimeRange": {
      "beginDate": timestamp,
      "endDate": timestamp
    },
    "completionTimeRange": {
      "beginDate": timestamp,
      "endDate": timestamp
    },
    "stateChangeTimeRange": {
      "beginDate": timestamp,
      "endDate": timestamp
    }
  }



``--next-token`` (string)


  You can use this parameter when paginating results. Set the value of this parameter to null on your first call to the **list-assessment-runs** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from the previous response to continue listing data.

  

``--max-results`` (integer)


  You can use this parameter to indicate the maximum number of items that you want in the response. The default value is 10. The maximum value is 500.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list assessment runs**

The following ``list-assessment-runs`` command lists all existing assessment runs::

  aws inspector list-assessment-runs

Output::

{
  "assessmentRunArns": 
  [
  "arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-4r1V2mAw/run/0-MKkpXXPE",
  "arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-4r1V2mAw/run/0-v5D6fI3v"
  ]
}

For more information, see `Amazon Inspector Assessment Templates and Assessment Runs`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Assessment Templates and Assessment Runs`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_assessments.html



======
Output
======

assessmentRunArns -> (list)

  

  A list of ARNs that specifies the assessment runs that are returned by the action.

  

  (string)

    

    

  

nextToken -> (string)

  

  When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to null.

  

  

