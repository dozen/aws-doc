[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms tag-resource:


************
tag-resource
************



===========
Description
===========



Adds or overwrites one or more tags for the specified customer master key (CMK). 

 

Each tag consists of a tag key and a tag value. Tag keys and tag values are both required, but tag values can be empty (null) strings.

 

You cannot use the same tag key more than once per CMK. For example, consider a CMK with one tag whose tag key is ``Purpose`` and tag value is ``Test`` . If you send a ``tag-resource`` request for this CMK with a tag key of ``Purpose`` and a tag value of ``Prod`` , it does not create a second tag. Instead, the original tag is overwritten with the new tag value.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/TagResource>`_


========
Synopsis
========

::

    tag-resource
  --key-id <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--key-id`` (string)


  A unique identifier for the CMK you are tagging. You can use the unique key ID or the Amazon Resource Name (ARN) of the CMK. Examples:

   

   
  * Unique key ID: ``1234abcd-12ab-34cd-56ef-1234567890ab``   
   
  * Key ARN: ``arn:aws:kms:us-east-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab``   
   

  

``--tags`` (list)


  One or more tags. Each tag consists of a tag key and a tag value.

  



Shorthand Syntax::

    TagKey=string,TagValue=string ...




JSON Syntax::

  [
    {
      "TagKey": "string",
      "TagValue": "string"
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

None