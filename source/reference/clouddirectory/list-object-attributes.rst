[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory list-object-attributes:


**********************
list-object-attributes
**********************



===========
Description
===========



Lists all attributes that are associated with an object. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/ListObjectAttributes>`_


========
Synopsis
========

::

    list-object-attributes
  --directory-arn <value>
  --object-reference <value>
  [--next-token <value>]
  [--max-results <value>]
  [--consistency-level <value>]
  [--facet-filter <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  The Amazon Resource Name (ARN) that is associated with the  Directory where the object resides. For more information, see  arns .

  

``--object-reference`` (structure)


  The reference that identifies the object whose attributes will be listed.

  



Shorthand Syntax::

    Selector=string




JSON Syntax::

  {
    "Selector": "string"
  }



``--next-token`` (string)


  The pagination token.

  

``--max-results`` (integer)


  The maximum number of items to be retrieved in a single call. This is an approximate number.

  

``--consistency-level`` (string)


  Represents the manner and timing in which the successful write or update of an object is reflected in a subsequent read operation of that same object.

  

  Possible values:

  
  *   ``SERIALIZABLE``

  
  *   ``EVENTUAL``

  

  

``--facet-filter`` (structure)


  Used to filter the list of object attributes that are associated with a certain facet.

  



Shorthand Syntax::

    SchemaArn=string,FacetName=string




JSON Syntax::

  {
    "SchemaArn": "string",
    "FacetName": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Attributes -> (list)

  

  Attributes map that is associated with the object. ``AttributeArn`` is the key, and attribute value is the value.

  

  (structure)

    

    The combination of an attribute key and an attribute value.

    

    Key -> (structure)

      

      The key of the attribute.

      

      SchemaArn -> (string)

        

        The Amazon Resource Name (ARN) of the schema that contains the facet and attribute.

        

        

      FacetName -> (string)

        

        The name of the facet that the attribute exists within.

        

        

      Name -> (string)

        

        The name of the attribute.

        

        

      

    Value -> (structure)

      

      The value of the attribute.

      

      StringValue -> (string)

        

        A string data value.

        

        

      BinaryValue -> (blob)

        

        A binary data value.

        

        

      BooleanValue -> (boolean)

        

        A Boolean data value.

        

        

      NumberValue -> (string)

        

        A number data value.

        

        

      DatetimeValue -> (timestamp)

        

        A date and time value.

        

        

      

    

  

NextToken -> (string)

  

  The pagination token.

  

  

