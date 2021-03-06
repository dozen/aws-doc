[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector list-findings:


*************
list-findings
*************



===========
Description
===========



Lists findings that are generated by the assessment runs that are specified by the ARNs of the assessment runs.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/ListFindings>`_


========
Synopsis
========

::

    list-findings
  [--assessment-run-arns <value>]
  [--filter <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--assessment-run-arns`` (list)


  The ARNs of the assessment runs that generate the findings that you want to list.

  



Syntax::

  "string" "string" ...



``--filter`` (structure)


  You can use this parameter to specify a subset of data to be included in the action's response.

   

  For a record to match a filter, all specified filter attributes must match. When multiple values are specified for a filter attribute, any of the values can match.

  



Shorthand Syntax::

    agentIds=string,string,autoScalingGroups=string,string,ruleNames=string,string,severities=string,string,rulesPackageArns=string,string,attributes=[{key=string,value=string},{key=string,value=string}],userAttributes=[{key=string,value=string},{key=string,value=string}],creationTimeRange={beginDate=timestamp,endDate=timestamp}




JSON Syntax::

  {
    "agentIds": ["string", ...],
    "autoScalingGroups": ["string", ...],
    "ruleNames": ["string", ...],
    "severities": ["Low"|"Medium"|"High"|"Informational"|"Undefined", ...],
    "rulesPackageArns": ["string", ...],
    "attributes": [
      {
        "key": "string",
        "value": "string"
      }
      ...
    ],
    "userAttributes": [
      {
        "key": "string",
        "value": "string"
      }
      ...
    ],
    "creationTimeRange": {
      "beginDate": timestamp,
      "endDate": timestamp
    }
  }



``--next-token`` (string)


  You can use this parameter when paginating results. Set the value of this parameter to null on your first call to the **list-findings** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from the previous response to continue listing data.

  

``--max-results`` (integer)


  You can use this parameter to indicate the maximum number of items you want in the response. The default value is 10. The maximum value is 500.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list findings**

The following ``list-findings`` command lists all of the generated findings::

  aws inspector list-findings

Output::

   {
	   "findingArns": [
	   "arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-4r1V2mAw/run/0-MKkpXXPE/finding/0-HwPnsDm4",
	   "arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-4r1V2mAw/run/0-v5D6fI3v/finding/0-tyvmqBLy"
	 ]
   }

For more information, see `Amazon Inspector Findings`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Findings`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_findings.html



======
Output
======

findingArns -> (list)

  

  A list of ARNs that specifies the findings returned by the action.

  

  (string)

    

    

  

nextToken -> (string)

  

  When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to null.

  

  

