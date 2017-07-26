[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory list-index:


**********
list-index
**********



===========
Description
===========



Lists objects attached to the specified index.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/ListIndex>`_


========
Synopsis
========

::

    list-index
  --directory-arn <value>
  [--ranges-on-indexed-values <value>]
  --index-reference <value>
  [--max-results <value>]
  [--next-token <value>]
  [--consistency-level <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  The ARN of the directory that the index exists in.

  

``--ranges-on-indexed-values`` (list)


  Specifies the ranges of indexed values that you want to query.

  



Shorthand Syntax::

    AttributeKey={SchemaArn=string,FacetName=string,Name=string},Range={StartMode=string,StartValue={StringValue=string,BinaryValue=blob,BooleanValue=boolean,NumberValue=string,DatetimeValue=timestamp},EndMode=string,EndValue={StringValue=string,BinaryValue=blob,BooleanValue=boolean,NumberValue=string,DatetimeValue=timestamp}} ...




JSON Syntax::

  [
    {
      "AttributeKey": {
        "SchemaArn": "string",
        "FacetName": "string",
        "Name": "string"
      },
      "Range": {
        "StartMode": "FIRST"|"LAST"|"LAST_BEFORE_MISSING_VALUES"|"INCLUSIVE"|"EXCLUSIVE",
        "StartValue": {
          "StringValue": "string",
          "BinaryValue": blob,
          "BooleanValue": true|false,
          "NumberValue": "string",
          "DatetimeValue": timestamp
        },
        "EndMode": "FIRST"|"LAST"|"LAST_BEFORE_MISSING_VALUES"|"INCLUSIVE"|"EXCLUSIVE",
        "EndValue": {
          "StringValue": "string",
          "BinaryValue": blob,
          "BooleanValue": true|false,
          "NumberValue": "string",
          "DatetimeValue": timestamp
        }
      }
    }
    ...
  ]



``--index-reference`` (structure)


  The reference to the index to list.

  



Shorthand Syntax::

    Selector=string




JSON Syntax::

  {
    "Selector": "string"
  }



``--max-results`` (integer)


  The maximum number of results to retrieve from the index.

  

``--next-token`` (string)


  The pagination token.

  

``--consistency-level`` (string)


  The consistency level to execute the request at.

  

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

  

  The objects and indexed values attached to the index.

  

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

  

  

