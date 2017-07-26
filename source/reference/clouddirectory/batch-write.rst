[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory batch-write:


***********
batch-write
***********



===========
Description
===========



Performs all the write operations in a batch. Either all the operations succeed or none. Batch writes supports only object-related operations.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/BatchWrite>`_


========
Synopsis
========

::

    batch-write
  --directory-arn <value>
  --operations <value>
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
      "CreateObject": {
        "SchemaFacet": [
          {
            "SchemaArn": "string",
            "FacetName": "string"
          }
          ...
        ],
        "ObjectAttributeList": [
          {
            "Key": {
              "SchemaArn": "string",
              "FacetName": "string",
              "Name": "string"
            },
            "Value": {
              "StringValue": "string",
              "BinaryValue": blob,
              "BooleanValue": true|false,
              "NumberValue": "string",
              "DatetimeValue": timestamp
            }
          }
          ...
        ],
        "ParentReference": {
          "Selector": "string"
        },
        "LinkName": "string",
        "BatchReferenceName": "string"
      },
      "AttachObject": {
        "ParentReference": {
          "Selector": "string"
        },
        "ChildReference": {
          "Selector": "string"
        },
        "LinkName": "string"
      },
      "DetachObject": {
        "ParentReference": {
          "Selector": "string"
        },
        "LinkName": "string",
        "BatchReferenceName": "string"
      },
      "UpdateObjectAttributes": {
        "ObjectReference": {
          "Selector": "string"
        },
        "AttributeUpdates": [
          {
            "ObjectAttributeKey": {
              "SchemaArn": "string",
              "FacetName": "string",
              "Name": "string"
            },
            "ObjectAttributeAction": {
              "ObjectAttributeActionType": "CREATE_OR_UPDATE"|"DELETE",
              "ObjectAttributeUpdateValue": {
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
      },
      "DeleteObject": {
        "ObjectReference": {
          "Selector": "string"
        }
      },
      "AddFacetToObject": {
        "SchemaFacet": {
          "SchemaArn": "string",
          "FacetName": "string"
        },
        "ObjectAttributeList": [
          {
            "Key": {
              "SchemaArn": "string",
              "FacetName": "string",
              "Name": "string"
            },
            "Value": {
              "StringValue": "string",
              "BinaryValue": blob,
              "BooleanValue": true|false,
              "NumberValue": "string",
              "DatetimeValue": timestamp
            }
          }
          ...
        ],
        "ObjectReference": {
          "Selector": "string"
        }
      },
      "RemoveFacetFromObject": {
        "SchemaFacet": {
          "SchemaArn": "string",
          "FacetName": "string"
        },
        "ObjectReference": {
          "Selector": "string"
        }
      },
      "AttachPolicy": {
        "PolicyReference": {
          "Selector": "string"
        },
        "ObjectReference": {
          "Selector": "string"
        }
      },
      "CreateIndex": {
        "OrderedIndexedAttributeList": [
          {
            "SchemaArn": "string",
            "FacetName": "string",
            "Name": "string"
          }
          ...
        ],
        "IsUnique": true|false,
        "ParentReference": {
          "Selector": "string"
        },
        "LinkName": "string",
        "BatchReferenceName": "string"
      },
      "AttachToIndex": {
        "IndexReference": {
          "Selector": "string"
        },
        "TargetReference": {
          "Selector": "string"
        }
      },
      "DetachFromIndex": {
        "IndexReference": {
          "Selector": "string"
        },
        "TargetReference": {
          "Selector": "string"
        }
      },
      "AttachTypedLink": {
        "SourceObjectReference": {
          "Selector": "string"
        },
        "TargetObjectReference": {
          "Selector": "string"
        },
        "TypedLinkFacet": {
          "SchemaArn": "string",
          "TypedLinkName": "string"
        },
        "Attributes": [
          {
            "AttributeName": "string",
            "Value": {
              "StringValue": "string",
              "BinaryValue": blob,
              "BooleanValue": true|false,
              "NumberValue": "string",
              "DatetimeValue": timestamp
            }
          }
          ...
        ]
      },
      "DetachTypedLink": {
        "TypedLinkSpecifier": {
          "TypedLinkFacet": {
            "SchemaArn": "string",
            "TypedLinkName": "string"
          },
          "SourceObjectReference": {
            "Selector": "string"
          },
          "TargetObjectReference": {
            "Selector": "string"
          },
          "IdentityAttributeValues": [
            {
              "AttributeName": "string",
              "Value": {
                "StringValue": "string",
                "BinaryValue": blob,
                "BooleanValue": true|false,
                "NumberValue": "string",
                "DatetimeValue": timestamp
              }
            }
            ...
          ]
        }
      }
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

Responses -> (list)

  

  A list of all the responses for each batch write.

  

  (structure)

    

    Represents the output of a ``batch-write`` response operation.

    

    CreateObject -> (structure)

      

      Creates an object in a  Directory .

      

      ObjectIdentifier -> (string)

        

        The ID that is associated with the object.

        

        

      

    AttachObject -> (structure)

      

      Attaches an object to a  Directory .

      

      attachedObjectIdentifier -> (string)

        

        The ``ObjectIdentifier`` of the object that has been attached.

        

        

      

    DetachObject -> (structure)

      

      Detaches an object from a  Directory .

      

      detachedObjectIdentifier -> (string)

        

        The ``ObjectIdentifier`` of the detached object.

        

        

      

    UpdateObjectAttributes -> (structure)

      

      Updates a given object’s attributes.

      

      ObjectIdentifier -> (string)

        

        ID that is associated with the object.

        

        

      

    DeleteObject -> (structure)

      

      Deletes an object in a  Directory .

      

      

    AddFacetToObject -> (structure)

      

      The result of an add facet to object batch operation.

      

      

    RemoveFacetFromObject -> (structure)

      

      The result of a batch remove facet from object operation.

      

      

    AttachPolicy -> (structure)

      

      Attaches a policy object to a regular object. An object can have a limited number of attached policies.

      

      

    CreateIndex -> (structure)

      

      Creates an index object. See `Indexing <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/cd_indexing.html>`_ for more information.

      

      ObjectIdentifier -> (string)

        

        The ``ObjectIdentifier`` of the index created by this operation.

        

        

      

    AttachToIndex -> (structure)

      

      Attaches the specified object to the specified index.

      

      AttachedObjectIdentifier -> (string)

        

        The ``ObjectIdentifier`` of the object that was attached to the index.

        

        

      

    DetachFromIndex -> (structure)

      

      Detaches the specified object from the specified index.

      

      DetachedObjectIdentifier -> (string)

        

        The ``ObjectIdentifier`` of the object that was detached from the index.

        

        

      

    AttachTypedLink -> (structure)

      

      Attaches a typed link to a specified source and target object. For more information, see `Typed link <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/objectsandlinks.html#typedlink>`_ .

      

      TypedLinkSpecifier -> (structure)

        

        Returns a typed link specifier as output.

        

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

                

                

              

            

          

        

      

    DetachTypedLink -> (structure)

      

      Detaches a typed link from a specified source and target object. For more information, see `Typed link <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/objectsandlinks.html#typedlink>`_ .

      

      

    

  

