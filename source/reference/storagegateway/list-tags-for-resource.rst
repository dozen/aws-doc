[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway list-tags-for-resource:


**********************
list-tags-for-resource
**********************



===========
Description
===========



This operation lists the tags that have been added to the specified resource. 



========
Synopsis
========

::

    list-tags-for-resource
  --resource-arn <value>
  [--marker <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-arn`` (string)


  The Amazon Resource Name (ARN) of the resource for which you want to list tags.

  

``--marker`` (string)


  An opaque string that indicates the position at which to begin returning the list of tags.

  

``--limit`` (integer)


  Specifies that the list of tags returned be limited to the specified number of items.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ResourceARN -> (string)

  

  he Amazon Resource Name (ARN) of the resource for which you want to list tags.

  

  

Marker -> (string)

  

  An opaque string that indicates the position at which to stop returning the list of tags.

  

  

Tags -> (list)

  

  An array that contains the tags for the specified resource.

  

  (structure)

    

    Key -> (string)

      

      

    Value -> (string)

      

      

    

  

