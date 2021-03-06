[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector describe-rules-packages:


***********************
describe-rules-packages
***********************



===========
Description
===========



Describes the rules packages that are specified by the ARNs of the rules packages.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/DescribeRulesPackages>`_


========
Synopsis
========

::

    describe-rules-packages
  --rules-package-arns <value>
  [--locale <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rules-package-arns`` (list)


  The ARN that specifies the rules package that you want to describe.

  



Syntax::

  "string" "string" ...



``--locale`` (string)


  The locale that you want to translate a rules package description into.

  

  Possible values:

  
  *   ``EN_US``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe rules packages**

The following ``describe-rules-packages`` command describes the rules package with the ARN of ``arn:aws:inspector:us-west-2:758058086616:rulespackage/0-9hgA516p``::

  aws inspector describe-rules-packages --rules-package-arns arn:aws:inspector:us-west-2:758058086616:rulespackage/0-9hgA516p

Output::

   {
	 "failedItems": {},
	 "rulesPackages": [
	   {
		 "arn": "arn:aws:inspector:us-west-2:758058086616:rulespackage/0-9hgA516p",
		 "description": "The rules in this package help verify whether the EC2 instances in your application are exposed to Common Vulnerabilities and 
		 Exposures (CVEs). Attacks can exploit unpatched vulnerabilities to compromise the confidentiality, integrity, or availability of your service 
		 or data. The CVE system provides a reference for publicly known information security vulnerabilities and exposures. For more information, see 
		 [https://cve.mitre.org/](https://cve.mitre.org/). If a particular CVE appears in one of the produced Findings at the end of a completed 
		 Inspector assessment, you can search [https://cve.mitre.org/](https://cve.mitre.org/) using the CVE's ID (for example, \"CVE-2009-0021\") to 
		 find detailed information about this CVE, its severity, and how to mitigate it. ",
		 "name": "Common Vulnerabilities and Exposures",
		 "provider": "Amazon Web Services, Inc.",
		 "version": "1.1"
	   }
	 ]
   } 

For more information, see `Amazon Inspector Rules Packages and Rules`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Rules Packages and Rules`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_rule-packages.html



======
Output
======

rulesPackages -> (list)

  

  Information about the rules package.

  

  (structure)

    

    Contains information about an Amazon Inspector rules package. This data type is used as the response element in the  describe-rules-packages action.

    

    arn -> (string)

      

      The ARN of the rules package.

      

      

    name -> (string)

      

      The name of the rules package.

      

      

    version -> (string)

      

      The version ID of the rules package.

      

      

    provider -> (string)

      

      The provider of the rules package.

      

      

    description -> (string)

      

      The description of the rules package.

      

      

    

  

failedItems -> (map)

  

  Rules package details that cannot be described. An error code is provided for each failed item.

  

  key -> (string)

    

    

  value -> (structure)

    

    Includes details about the failed items.

    

    failureCode -> (string)

      

      The status code of a failed item.

      

      

    retryable -> (boolean)

      

      Indicates whether you can immediately retry a request for this item for a specified resource.

      

      

    

  

