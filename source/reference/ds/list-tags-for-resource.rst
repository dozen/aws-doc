[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds list-tags-for-resource:


**********************
list-tags-for-resource
**********************



===========
Description
===========



Lists all tags on a directory.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/ListTagsForResource>`_


========
Synopsis
========

::

    list-tags-for-resource
  --resource-id <value>
  [--next-token <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-id`` (string)


  Identifier (ID) of the directory for which you want to retrieve tags.

  

``--next-token`` (string)


  Reserved for future use.

  

``--limit`` (integer)


  Reserved for future use.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Tags -> (list)

  

  List of tags returned by the list-tags-for-resource operation.

  

  (structure)

    

    Metadata assigned to a directory consisting of a key-value pair.

    

    Key -> (string)

      

      Required name of the tag. The string value can be Unicode characters and cannot be prefixed with "aws:". The string can contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

      

      

    Value -> (string)

      

      The optional value of the tag. The string value can be Unicode characters. The string can contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

      

      

    

  

NextToken -> (string)

  

  Reserved for future use.

  

  

