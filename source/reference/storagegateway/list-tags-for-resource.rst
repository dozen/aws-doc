[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway list-tags-for-resource:


**********************
list-tags-for-resource
**********************



===========
Description
===========



Lists the tags that have been added to the specified resource. This operation is only supported in the cached volume, stored volume and tape gateway architecture.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/ListTagsForResource>`_


========
Synopsis
========

::

    list-tags-for-resource
  --resource-arn <value>
  [--marker <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      

    

  

