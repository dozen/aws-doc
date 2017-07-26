[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway remove-tags-from-resource:


*************************
remove-tags-from-resource
*************************



===========
Description
===========



Removes one or more tags from the specified resource. This operation is only supported in the cached volume, stored volume and tape gateway architectures.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/RemoveTagsFromResource>`_


========
Synopsis
========

::

    remove-tags-from-resource
  --resource-arn <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn`` (string)


  The Amazon Resource Name (ARN) of the resource you want to remove the tags from.

  

``--tag-keys`` (list)


  The keys of the tags you want to remove from the specified resource. A tag is composed of a key/value pair.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ResourceARN -> (string)

  

  The Amazon Resource Name (ARN) of the resource that the tags were removed from.

  

  

