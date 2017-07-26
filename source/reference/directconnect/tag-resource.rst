[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect tag-resource:


************
tag-resource
************



===========
Description
===========



Adds the specified tags to the specified Direct Connect resource. Each Direct Connect resource can have a maximum of 50 tags.

 

Each tag consists of a key and an optional value. If a tag with the same key is already associated with the Direct Connect resource, this action updates its value.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/directconnect-2012-10-25/TagResource>`_


========
Synopsis
========

::

    tag-resource
  --resource-arn <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn`` (string)


  The Amazon Resource Name (ARN) of the Direct Connect resource.

   

  Example: arn:aws:directconnect:us-east-1:123456789012:dxcon/dxcon-fg5678gh

  

``--tags`` (list)


  The list of tags to add.

  



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

**To add a tag to an AWS Direct Connect resource**

The following command adds a tag with a key of ``Name`` and a value of ``VAConnection`` to the connection ``dxcon-abcabc12``. If the command succeeds, no output is returned.

Command::

  aws directconnect tag-resource --resource-arn arn:aws:directconnect:us-east-1:123456789012:dxcon/dxcon-abcabc12 --tags "key=Name,value=VAConnection"



======
Output
======

