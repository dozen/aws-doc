[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis list-tags-for-stream:


********************
list-tags-for-stream
********************



===========
Description
===========



Lists the tags for the specified Amazon Kinesis stream.



========
Synopsis
========

::

    list-tags-for-stream
  --stream-name <value>
  [--exclusive-start-tag-key <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stream-name`` (string)


  The name of the stream.

  

``--exclusive-start-tag-key`` (string)


  The key to use as the starting point for the list of tags. If this parameter is set, ``list-tags-for-stream`` gets all tags that occur after ``ExclusiveStartTagKey`` . 

  

``--limit`` (integer)


  The number of tags to return. If this number is less than the total number of tags associated with the stream, ``HasMoreTags`` is set to ``true`` . To list additional tags, set ``ExclusiveStartTagKey`` to the last key in the response.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Tags -> (list)

  

  A list of tags associated with ``stream-name`` , starting with the first tag after ``ExclusiveStartTagKey`` and up to the specified ``Limit`` . 

  

  (structure)

    

    Metadata assigned to the stream, consisting of a key-value pair.

    

    Key -> (string)

      

      A unique identifier for the tag. Maximum length: 128 characters. Valid characters: Unicode letters, digits, white space, _ . / = + - % @

      

      

    Value -> (string)

      

      An optional string, typically used to describe or define the tag. Maximum length: 256 characters. Valid characters: Unicode letters, digits, white space, _ . / = + - % @

      

      

    

  

HasMoreTags -> (boolean)

  

  If set to ``true`` , more tags are available. To request additional tags, set ``ExclusiveStartTagKey`` to the key of the last tag returned.

  

  

