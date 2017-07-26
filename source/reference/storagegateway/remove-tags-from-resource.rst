[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway remove-tags-from-resource:


*************************
remove-tags-from-resource
*************************



===========
Description
===========



This operation removes one or more tags from the specified resource.



========
Synopsis
========

::

    remove-tags-from-resource
  --resource-arn <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ResourceARN -> (string)

  

  The Amazon Resource Name (ARN) of the resource that the tags were removed from.

  

  

