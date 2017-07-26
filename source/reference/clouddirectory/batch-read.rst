[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory batch-read:


**********
batch-read
**********



===========
Description
===========



Performs all the read operations in a batch. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/BatchRead>`_


========
Synopsis
========

::

    batch-read
  --directory-arn <value>
  --operations <value>
  [--consistency-level <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  The Amazon Resource Name (ARN) that is associated with the  Directory . For more information, see  arns .

  

``--operations`` (list)


  A list of operations that are part of the batch.

  



JSON Syntax::

  [
    {
      "ListObjectAttributes": {
        "ObjectReference": {
          "Selector": "string"
        },
        "NextToken": "string",
        "MaxResults": integer,
        "FacetFilter": {
          "SchemaArn": "string",
          "FacetName": "string"
        }
      },
      "ListObjectChildren": {
        "ObjectReference": {
          "Selector": "string"
        },
        "NextToken": "string",
        "MaxResults": integer
      },
      "ListAttachedIndices": {
        "TargetReference": {
          "Selector": "string"
        },
        "NextToken": "string",
        "MaxResults": integer
      },
      "ListObjectParentPaths": {
        "ObjectReference": {
          "Selector": "string"
        },
        "NextToken": "string",
        "MaxResults": integer
      },
      "GetObjectInformation": {
        "ObjectReference": {
          "Selector": "string"
        }
      },
      "ListObjectPolicies": {
        "ObjectReference": {
          "Selector": "string"
        },
        "NextToken": "string",
        "MaxResults": integer
      },
      "ListPolicyAttachments": {
        "PolicyReference": {
          "Selector": "string"
        },
        "NextToken": "string",
        "MaxResults": integer
      },
      "LookupPolicy": {
        "ObjectReference": {
          "Selector": "string"
        },
        "NextToken": "string",
        "MaxResults": integer
      },
      "ListIndex": {
        "RangesOnIndexedValues": [
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
        ],
        "IndexReference": {
          "Selector": "string"
        },
        "MaxResults": integer,
        "NextToken": "string"
      },
      "ListOutgoingTypedLinks": {
        "ObjectReference": {
          "Selector": "string"
        },
        "FilterAttributeRanges": [
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
        ],
        "FilterTypedLink": {
          "SchemaArn": "string",
          "TypedLinkName": "string"
        },
        "NextToken": "string",
        "MaxResults": integer
      },
      "ListIncomingTypedLinks": {
        "ObjectReference": {
          "Selector": "string"
        },
        "FilterAttributeRanges": [
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
        ],
        "FilterTypedLink": {
          "SchemaArn": "string",
          "TypedLinkName": "string"
        },
        "NextToken": "string",
        "MaxResults": integer
      }
    }
    ...
  ]



``--consistency-level`` (string)


  Represents the manner and timing in which the successful write or update of an object is reflected in a subsequent read operation of that same object.

  

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

Responses -> (list)

  

  A list of all the responses for each batch read.

  

  (structure)

    

    Represents the output of a ``batch-read`` response operation.

    

    SuccessfulResponse -> (structure)

      

      Identifies which operation in a batch has succeeded.

      

      ListObjectAttributes -> (structure)

        

        Lists all attributes that are associated with an object.

        

        Attributes -> (list)

          

          The attributes map that is associated with the object. ``AttributeArn`` is the key; attribute value is the value.

          

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

          

          

        

      ListObjectChildren -> (structure)

        

        Returns a paginated list of child objects that are associated with a given object.

        

        Children -> (map)

          

          The children structure, which is a map with the key as the ``LinkName`` and ``ObjectIdentifier`` as the value.

          

          key -> (string)

            

            

          value -> (string)

            

            

          

        NextToken -> (string)

          

          The pagination token.

          

          

        

      GetObjectInformation -> (structure)

        

        Retrieves metadata about an object.

        

        SchemaFacets -> (list)

          

          The facets attached to the specified object.

          

          (structure)

            

            A facet.

            

            SchemaArn -> (string)

              

              The ARN of the schema that contains the facet.

              

              

            FacetName -> (string)

              

              The name of the facet.

              

              

            

          

        ObjectIdentifier -> (string)

          

          The ``ObjectIdentifier`` of the specified object.

          

          

        

      ListAttachedIndices -> (structure)

        

        Lists indices attached to an object.

        

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

          

          

        

      ListObjectParentPaths -> (structure)

        

        Retrieves all available parent paths for any object type such as node, leaf node, policy node, and index node objects. For more information about objects, see `Directory Structure <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/cd_key_concepts.html#dirstructure>`_ .

        

        PathToObjectIdentifiersList -> (list)

          

          Returns the path to the ``ObjectIdentifiers`` that are associated with the directory.

          

          (structure)

            

            Returns the path to the ``ObjectIdentifiers`` that is associated with the directory.

            

            Path -> (string)

              

              The path that is used to identify the object starting from directory root.

              

              

            ObjectIdentifiers -> (list)

              

              Lists ``ObjectIdentifiers`` starting from directory root to the object in the request.

              

              (string)

                

                

              

            

          

        NextToken -> (string)

          

          The pagination token.

          

          

        

      ListObjectPolicies -> (structure)

        

        Returns policies attached to an object in pagination fashion.

        

        AttachedPolicyIds -> (list)

          

          A list of policy ``ObjectIdentifiers`` , that are attached to the object.

          

          (string)

            

            

          

        NextToken -> (string)

          

          The pagination token.

          

          

        

      ListPolicyAttachments -> (structure)

        

        Returns all of the ``ObjectIdentifiers`` to which a given policy is attached.

        

        ObjectIdentifiers -> (list)

          

          A list of ``ObjectIdentifiers`` to which the policy is attached.

          

          (string)

            

            

          

        NextToken -> (string)

          

          The pagination token.

          

          

        

      LookupPolicy -> (structure)

        

        Lists all policies from the root of the  Directory to the object specified. If there are no policies present, an empty list is returned. If policies are present, and if some objects don't have the policies attached, it returns the ``ObjectIdentifier`` for such objects. If policies are present, it returns ``ObjectIdentifier`` , ``policyId`` , and ``policyType`` . Paths that don't lead to the root from the target object are ignored. For more information, see `Policies <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/cd_key_concepts.html#policies>`_ .

        

        PolicyToPathList -> (list)

          

          Provides list of path to policies. Policies contain ``PolicyId`` , ``ObjectIdentifier`` , and ``PolicyType`` . For more information, see `Policies <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/cd_key_concepts.html#policies>`_ .

          

          (structure)

            

            Used when a regular object exists in a  Directory and you want to find all of the policies that are associated with that object and the parent to that object.

            

            Path -> (string)

              

              The path that is referenced from the root.

              

              

            Policies -> (list)

              

              List of policy objects.

              

              (structure)

                

                Contains the ``PolicyType`` , ``PolicyId`` , and the ``ObjectIdentifier`` to which it is attached. For more information, see `Policies <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/cd_key_concepts.html#policies>`_ .

                

                PolicyId -> (string)

                  

                  The ID of ``PolicyAttachment`` .

                  

                  

                ObjectIdentifier -> (string)

                  

                  The ``ObjectIdentifier`` that is associated with ``PolicyAttachment`` .

                  

                  

                PolicyType -> (string)

                  

                  The type of policy that can be associated with ``PolicyAttachment`` .

                  

                  

                

              

            

          

        NextToken -> (string)

          

          The pagination token.

          

          

        

      ListIndex -> (structure)

        

        Lists objects attached to the specified index.

        

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

          

          

        

      ListOutgoingTypedLinks -> (structure)

        

        Returns a paginated list of all the outgoing  TypedLinkSpecifier information for an object. It also supports filtering by typed link facet and identity attributes. For more information, see `Typed link <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/objectsandlinks.html#typedlink>`_ .

        

        TypedLinkSpecifiers -> (list)

          

          Returns a typed link specifier as output.

          

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

          

          

        

      ListIncomingTypedLinks -> (structure)

        

        Returns a paginated list of all the incoming  TypedLinkSpecifier information for an object. It also supports filtering by typed link facet and identity attributes. For more information, see `Typed link <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/objectsandlinks.html#typedlink>`_ .

        

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

          

          

        

      

    ExceptionResponse -> (structure)

      

      Identifies which operation in a batch has failed.

      

      Type -> (string)

        

        A type of exception, such as ``InvalidArnException`` .

        

        

      Message -> (string)

        

        An exception message that is associated with the failure.

        

        

      

    

  

