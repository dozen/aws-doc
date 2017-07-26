[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector add-attributes-to-findings:


**************************
add-attributes-to-findings
**************************



===========
Description
===========



Assigns attributes (key and value pairs) to the findings that are specified by the ARNs of the findings.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/AddAttributesToFindings>`_


========
Synopsis
========

::

    add-attributes-to-findings
  --finding-arns <value>
  --attributes <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--finding-arns`` (list)


  The ARNs that specify the findings that you want to assign attributes to.

  



Syntax::

  "string" "string" ...



``--attributes`` (list)


  The array of attributes that you want to assign to specified findings.

  



Shorthand Syntax::

    key=string,value=string ...




JSON Syntax::

  [
    {
      "key": "string",
      "value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To add attributes to findings**

The following ``add-attribute-to-finding`` command assigns an attribute with the key of ``Example`` and value of ``example`` to the finding with the ARN of ``arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-8l1VIE0D/run/0-Z02cjjug/finding/0-T8yM9mEU``::

	aws inspector add-attributes-to-findings --finding-arns arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-8l1VIE0D/run/0-Z02cjjug/finding/0-T8yM9mEU --attributes key=Example,value=example

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

  

  Attribute details that cannot be described. An error code is provided for each failed item.

  

  key -> (string)

    

    

  value -> (structure)

    

    Includes details about the failed items.

    

    failureCode -> (string)

      

      The status code of a failed item.

      

      

    retryable -> (boolean)

      

      Indicates whether you can immediately retry a request for this item for a specified resource.

      

      

    

  

