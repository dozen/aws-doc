[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory list-incoming-typed-links:


*************************
list-incoming-typed-links
*************************



===========
Description
===========



Returns a paginated list of all the incoming  TypedLinkSpecifier information for an object. It also supports filtering by typed link facet and identity attributes. For more information, see `Typed link <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/objectsandlinks.html#typedlink>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/ListIncomingTypedLinks>`_


========
Synopsis
========

::

    list-incoming-typed-links
  --directory-arn <value>
  --object-reference <value>
  [--filter-attribute-ranges <value>]
  [--filter-typed-link <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--consistency-level <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  The Amazon Resource Name (ARN) of the directory where you want to list the typed links.

  

``--object-reference`` (structure)


  Reference that identifies the object whose attributes will be listed.

  



Shorthand Syntax::

    Selector=string




JSON Syntax::

  {
    "Selector": "string"
  }



``--filter-attribute-ranges`` (list)


  Provides range filters for multiple attributes. When providing ranges to typed link selection, any inexact ranges must be specified at the end. Any attributes that do not have a range specified are presumed to match the entire range.

  



Shorthand Syntax::

    AttributeName=string,Range={StartMode=string,StartValue={StringValue=string,BinaryValue=blob,BooleanValue=boolean,NumberValue=string,DatetimeValue=timestamp},EndMode=string,EndValue={StringValue=string,BinaryValue=blob,BooleanValue=boolean,NumberValue=string,DatetimeValue=timestamp}} ...




JSON Syntax::

  [
    {
      "AttributeName": "string",
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



``--filter-typed-link`` (structure)


  Filters are interpreted in the order of the attributes on the typed link facet, not the order in which they are supplied to any API calls.

  



Shorthand Syntax::

    SchemaArn=string,TypedLinkName=string




JSON Syntax::

  {
    "SchemaArn": "string",
    "TypedLinkName": "string"
  }



``--next-token`` (string)


  The pagination token.

  

``--max-results`` (integer)


  The maximum number of results to retrieve.

  

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

LinkSpecifiers -> (list)

  

  Returns one or more typed link specifiers as output.

  

  (structure)

    

    Contains all the information that is used to uniquely identify a typed link. The parameters discussed in this topic are used to uniquely specify the typed link being operated on. The  attach-typed-link API returns a typed link specifier while the  detach-typed-link API accepts one as input. Similarly, the  list-incoming-typed-links and  list-outgoing-typed-links API operations provide typed link specifiers as output. You can also construct a typed link specifier from scratch.

    

    TypedLinkFacet -> (structure)

      

      Identifies the typed link facet that is associated with the typed link.

      

      SchemaArn -> (string)

        

        The Amazon Resource Name (ARN) that is associated with the schema. For more information, see  arns .

        

        

      TypedLinkName -> (string)

        

        The unique name of the typed link facet.

        

        

      

    SourceObjectReference -> (structure)

      

      Identifies the source object that the typed link will attach to.

      

      Selector -> (string)

        

        A path selector supports easy selection of an object by the parent/child links leading to it from the directory root. Use the link names from each parent/child link to construct the path. Path selectors start with a slash (/) and link names are separated by slashes. For more information about paths, see `Accessing Objects <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/objectsandlinks.html#accessingobjects>`_ . You can identify an object in one of the following ways:

         

         
        * *$ObjectIdentifier* - An object identifier is an opaque string provided by Amazon Cloud Directory. When creating objects, the system will provide you with the identifier of the created object. An object’s identifier is immutable and no two objects will ever share the same object identifier 
         
        * */some/path* - Identifies the object based on path 
         
        * *#SomeBatchReference* - Identifies the object in a batch call 
         

        

        

      

    TargetObjectReference -> (structure)

      

      Identifies the target object that the typed link will attach to.

      

      Selector -> (string)

        

        A path selector supports easy selection of an object by the parent/child links leading to it from the directory root. Use the link names from each parent/child link to construct the path. Path selectors start with a slash (/) and link names are separated by slashes. For more information about paths, see `Accessing Objects <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/objectsandlinks.html#accessingobjects>`_ . You can identify an object in one of the following ways:

         

         
        * *$ObjectIdentifier* - An object identifier is an opaque string provided by Amazon Cloud Directory. When creating objects, the system will provide you with the identifier of the created object. An object’s identifier is immutable and no two objects will ever share the same object identifier 
         
        * */some/path* - Identifies the object based on path 
         
        * *#SomeBatchReference* - Identifies the object in a batch call 
         

        

        

      

    IdentityAttributeValues -> (list)

      

      Identifies the attribute value to update.

      

      (structure)

        

        Identifies the attribute name and value for a typed link.

        

        AttributeName -> (string)

          

          The attribute name of the typed link.

          

          

        Value -> (structure)

          

          The value for the typed link.

          

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

  

  

