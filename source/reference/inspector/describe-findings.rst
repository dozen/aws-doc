[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector describe-findings:


*****************
describe-findings
*****************



===========
Description
===========



Describes the findings that are specified by the ARNs of the findings.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/DescribeFindings>`_


========
Synopsis
========

::

    describe-findings
  --finding-arns <value>
  [--locale <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--finding-arns`` (list)


  The ARN that specifies the finding that you want to describe.

  



Syntax::

  "string" "string" ...



``--locale`` (string)


  The locale into which you want to translate a finding description, recommendation, and the short description that identifies the finding.

  

  Possible values:

  
  *   ``EN_US``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe findings**

The following ``describe-findings`` command describes the finding with the ARN of ``arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-4r1V2mAw/run/0-MKkpXXPE/finding/0-HwPnsDm4``::

  aws inspector describe-findings --finding-arns arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-4r1V2mAw/run/0-MKkpXXPE/finding/0-HwPnsDm4

Output::

   {
	 "failedItems": {},
	 "findings": [
	   {
		 "arn": "arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-4r1V2mAw/run/0-MKkpXXPE/finding/0-HwPnsDm4",
		 "assetAttributes": {
		   "ipv4Addresses": [],
		   "schemaVersion": 1
		 },
		 "assetType": "ec2-instance",
		 "attributes": [],
		 "confidence": 10,
		 "createdAt": 1458680301.37,
		 "description": "Amazon Inspector did not find any potential security issues during this assessment.",
		 "indicatorOfCompromise": false,
		 "numericSeverity": 0,
		 "recommendation": "No remediation needed.",
		 "schemaVersion": 1,
		 "service": "Inspector",
		 "serviceAttributes": {
		   "assessmentRunArn": "arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-4r1V2mAw/run/0-MKkpXXPE",
		   "rulesPackageArn": "arn:aws:inspector:us-west-2:758058086616:rulespackage/0-X1KXtawP",
		   "schemaVersion": 1
		 },
		 "severity": "Informational",
		 "title": "No potential security issues found",
		 "updatedAt": 1458680301.37,
		 "userAttributes": []
	   }
	 ]
   }  

For more information, see `Amazon Inspector Findings`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Findings`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_findings.html



======
Output
======

findings -> (list)

  

  Information about the finding.

  

  (structure)

    

    Contains information about an Amazon Inspector finding. This data type is used as the response element in the  describe-findings action.

    

    arn -> (string)

      

      The ARN that specifies the finding.

      

      

    schemaVersion -> (integer)

      

      The schema version of this data type.

      

      

    service -> (string)

      

      The data element is set to "Inspector".

      

      

    serviceAttributes -> (structure)

      

      This data type is used in the  Finding data type.

      

      schemaVersion -> (integer)

        

        The schema version of this data type.

        

        

      assessmentRunArn -> (string)

        

        The ARN of the assessment run during which the finding is generated.

        

        

      rulesPackageArn -> (string)

        

        The ARN of the rules package that is used to generate the finding.

        

        

      

    assetType -> (string)

      

      The type of the host from which the finding is generated.

      

      

    assetAttributes -> (structure)

      

      A collection of attributes of the host from which the finding is generated.

      

      schemaVersion -> (integer)

        

        The schema version of this data type.

        

        

      agentId -> (string)

        

        The ID of the agent that is installed on the EC2 instance where the finding is generated.

        

        

      autoScalingGroup -> (string)

        

        The Auto Scaling group of the EC2 instance where the finding is generated.

        

        

      amiId -> (string)

        

        The ID of the Amazon Machine Image (AMI) that is installed on the EC2 instance where the finding is generated.

        

        

      hostname -> (string)

        

        The hostname of the EC2 instance where the finding is generated.

        

        

      ipv4Addresses -> (list)

        

        The list of IP v4 addresses of the EC2 instance where the finding is generated.

        

        (string)

          

          

        

      

    id -> (string)

      

      The ID of the finding.

      

      

    title -> (string)

      

      The name of the finding.

      

      

    description -> (string)

      

      The description of the finding.

      

      

    recommendation -> (string)

      

      The recommendation for the finding.

      

      

    severity -> (string)

      

      The finding severity. Values can be set to High, Medium, Low, and Informational.

      

      

    numericSeverity -> (double)

      

      The numeric value of the finding severity.

      

      

    confidence -> (integer)

      

      This data element is currently not used.

      

      

    indicatorOfCompromise -> (boolean)

      

      This data element is currently not used.

      

      

    attributes -> (list)

      

      The system-defined attributes for the finding.

      

      (structure)

        

        This data type is used as a request parameter in the  add-attributes-to-findings and  create-assessment-template actions.

        

        key -> (string)

          

          The attribute key.

          

          

        value -> (string)

          

          The value assigned to the attribute key.

          

          

        

      

    userAttributes -> (list)

      

      The user-defined attributes that are assigned to the finding.

      

      (structure)

        

        This data type is used as a request parameter in the  add-attributes-to-findings and  create-assessment-template actions.

        

        key -> (string)

          

          The attribute key.

          

          

        value -> (string)

          

          The value assigned to the attribute key.

          

          

        

      

    createdAt -> (timestamp)

      

      The time when the finding was generated.

      

      

    updatedAt -> (timestamp)

      

      The time when  add-attributes-to-findings is called.

      

      

    

  

failedItems -> (map)

  

  Finding details that cannot be described. An error code is provided for each failed item.

  

  key -> (string)

    

    

  value -> (structure)

    

    Includes details about the failed items.

    

    failureCode -> (string)

      

      The status code of a failed item.

      

      

    retryable -> (boolean)

      

      Indicates whether you can immediately retry a request for this item for a specified resource.

      

      

    

  

