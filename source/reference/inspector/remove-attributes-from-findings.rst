[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector remove-attributes-from-findings:


*******************************
remove-attributes-from-findings
*******************************



===========
Description
===========



Removes entire attributes (key and value pairs) from the findings that are specified by the ARNs of the findings where an attribute with the specified key exists.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/RemoveAttributesFromFindings>`_


========
Synopsis
========

::

    remove-attributes-from-findings
  --finding-arns <value>
  --attribute-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--finding-arns`` (list)


  The ARNs that specify the findings that you want to remove attributes from.

  



Syntax::

  "string" "string" ...



``--attribute-keys`` (list)


  The array of attribute keys that you want to remove from specified findings.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To remove attributes from findings**

The following ``remove-attributes-from-finding`` command removes the attribute with the key of ``Example`` and value of ``example`` from the finding with the ARN of ``arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-8l1VIE0D/run/0-Z02cjjug/finding/0-T8yM9mEU``::

  aws inspector remove-attributes-from-findings --finding-arns arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-8l1VIE0D/run/0-Z02cjjug/finding/0-T8yM9mEU --attribute-keys key=Example,value=example

Output::

  {
	"failedItems": {}
  }

For more information, see `Amazon Inspector Findings`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Findings`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_findings.html



======
Output
======

failedItems -> (map)

  

  Attributes details that cannot be described. An error code is provided for each failed item.

  

  key -> (string)

    

    

  value -> (structure)

    

    Includes details about the failed items.

    

    failureCode -> (string)

      

      The status code of a failed item.

      

      

    retryable -> (boolean)

      

      Indicates whether you can immediately retry a request for this item for a specified resource.

      

      

    

  

