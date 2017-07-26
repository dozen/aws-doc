[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory list-attached-indices:


*********************
list-attached-indices
*********************



===========
Description
===========



Lists indices attached to an object.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/ListAttachedIndices>`_


========
Synopsis
========

::

    list-attached-indices
  --directory-arn <value>
  --target-reference <value>
  [--next-token <value>]
  [--max-results <value>]
  [--consistency-level <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  The ARN of the directory.

  

``--target-reference`` (structure)


  A reference to the object that has indices attached.

  



Shorthand Syntax::

    Selector=string




JSON Syntax::

  {
    "Selector": "string"
  }



``--next-token`` (string)


  The pagination token.

  

``--max-results`` (integer)


  The maximum number of results to retrieve.

  

``--consistency-level`` (string)


  The consistency level to use for this operation.

  

  Possible values:

  
  *   ``SERIALIZABLE``

  
  *   ``EVENTUAL``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IndexAttachments -> (list)

  

  The indices attached to the specified object.

  

  (structure)

    

    Represents an index and an attached object.

    

    IndexedAttributes -> (list)

      

      The indexed attribute values.

      

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

            

            

          

        

      

    ObjectIdentifier -> (string)

      

      The ``ObjectIdentifier`` of the object attached to the index.

      

      

    

  

NextToken -> (string)

  

  The pagination token.

  

  

