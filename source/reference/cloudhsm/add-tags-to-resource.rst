[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm add-tags-to-resource:


********************
add-tags-to-resource
********************



===========
Description
===========



Adds or overwrites one or more tags for the specified AWS CloudHSM resource.

 

Each tag consists of a key and a value. Tag keys must be unique to each resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudhsm-2014-05-30/AddTagsToResource>`_


========
Synopsis
========

::

    add-tags-to-resource
  --resource-arn <value>
  --tag-list <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn`` (string)


  The Amazon Resource Name (ARN) of the AWS CloudHSM resource to tag.

  

``--tag-list`` (list)


  One or more tags.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Status -> (string)

  

  The status of the operation.

  

  

