[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm remove-tags-from-resource:


*************************
remove-tags-from-resource
*************************



===========
Description
===========



Removes one or more tags from the specified AWS CloudHSM resource.

 

To remove a tag, specify only the tag key to remove (not the value). To overwrite the value for an existing tag, use  add-tags-to-resource .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudhsm-2014-05-30/RemoveTagsFromResource>`_


========
Synopsis
========

::

    remove-tags-from-resource
  --resource-arn <value>
  --tag-key-list <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn`` (string)


  The Amazon Resource Name (ARN) of the AWS CloudHSM resource.

  

``--tag-key-list`` (list)


  The tag key or keys to remove.

   

  Specify only the tag key to remove (not the value). To overwrite the value for an existing tag, use  add-tags-to-resource .

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Status -> (string)

  

  The status of the operation.

  

  

