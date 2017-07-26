[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds list-tags-for-resource:


**********************
list-tags-for-resource
**********************



===========
Description
===========



Lists all tags on an Amazon RDS resource.

 

For an overview on tagging an Amazon RDS resource, see `Tagging Amazon RDS Resources <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.Tagging.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/ListTagsForResource>`_


========
Synopsis
========

::

    list-tags-for-resource
  --resource-name <value>
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-name`` (string)


  The Amazon RDS resource with tags to be listed. This value is an Amazon Resource Name (ARN). For information about creating an ARN, see `Constructing an RDS Amazon Resource Name (ARN) <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Tagging.ARN.html#USER_Tagging.ARN.Constructing>`_ .

  

``--filters`` (list)


  This parameter is not currently supported.

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
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

TagList -> (list)

  

  List of tags returned by the list-tags-for-resource operation.

  

  (structure)

    

    Metadata assigned to an Amazon RDS resource consisting of a key-value pair.

    

    Key -> (string)

      

      A key is the required name of the tag. The string value can be from 1 to 128 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

      

      

    Value -> (string)

      

      A value is the optional value of the tag. The string value can be from 1 to 256 Unicode characters in length and cannot be prefixed with "aws:" or "rds:". The string can only contain only the set of Unicode letters, digits, white-space, '_', '.', '/', '=', '+', '-' (Java regex: "^([\\p{L}\\p{Z}\\p{N}_.:/=+\\-]*)$").

      

      

    

  

