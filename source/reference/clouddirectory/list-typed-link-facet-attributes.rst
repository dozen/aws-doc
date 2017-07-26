[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory list-typed-link-facet-attributes:


********************************
list-typed-link-facet-attributes
********************************



===========
Description
===========



Returns a paginated list of all attribute definitions for a particular  TypedLinkFacet . For more information, see `Typed link <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/objectsandlinks.html#typedlink>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/ListTypedLinkFacetAttributes>`_


========
Synopsis
========

::

    list-typed-link-facet-attributes
  --schema-arn <value>
  --name <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--schema-arn`` (string)


  The Amazon Resource Name (ARN) that is associated with the schema. For more information, see  arns .

  

``--name`` (string)


  The unique name of the typed link facet.

  

``--next-token`` (string)


  The pagination token.

  

``--max-results`` (integer)


  The maximum number of results to retrieve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Attributes -> (list)

  

  An ordered set of attributes associate with the typed link.

  

  (structure)

    

    A typed link attribute definition.

    

    Name -> (string)

      

      The unique name of the typed link attribute.

      

      

    Type -> (string)

      

      The type of the attribute.

      

      

    DefaultValue -> (structure)

      

      The default value of the attribute (if configured).

      

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

        

        

      

    IsImmutable -> (boolean)

      

      Whether the attribute is mutable or not.

      

      

    Rules -> (map)

      

      Validation rules that are attached to the attribute definition.

      

      key -> (string)

        

        

      value -> (structure)

        

        Contains an Amazon Resource Name (ARN) and parameters that are associated with the rule.

        

        Type -> (string)

          

          The type of attribute validation rule.

          

          

        Parameters -> (map)

          

          The minimum and maximum parameters that are associated with the rule.

          

          key -> (string)

            

            

          value -> (string)

            

            

          

        

      

    RequiredBehavior -> (string)

      

      The required behavior of the ``TypedLinkAttributeDefinition`` .

      

      

    

  

NextToken -> (string)

  

  The pagination token.

  

  

