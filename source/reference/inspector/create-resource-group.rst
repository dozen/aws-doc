[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector create-resource-group:


*********************
create-resource-group
*********************



===========
Description
===========



Creates a resource group using the specified set of tags (key and value pairs) that are used to select the EC2 instances to be included in an Amazon Inspector assessment target. The created resource group is then used to create an Amazon Inspector assessment target. For more information, see  create-assessment-target .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/CreateResourceGroup>`_


========
Synopsis
========

::

    create-resource-group
  --resource-group-tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-group-tags`` (list)


  A collection of keys and an array of possible values, '[{"key":"key1","values":["Value1","Value2"]},{"key":"Key2","values":["Value3"]}]'.

   

  For example,'[{"key":"Name","values":["TestEC2Instance"]}]'.

  



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

**To create a resource group**

The following ``create-resource-group`` command creates a resource group using the tag key of ``Name`` and value of ``example``::

  aws inspector create-resource-group --resource-group-tags key=Name,value=example

Output::

  {
     "resourceGroupArn": "arn:aws:inspector:us-west-2:123456789012:resourcegroup/0-AB6DMKnv"
  }

For more information, see `Amazon Inspector Assessment Targets`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Assessment Targets`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_applications.html



======
Output
======

resourceGroupArn -> (string)

  

  The ARN that specifies the resource group that is created.

  

  

