[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory update-facet:


************
update-facet
************



===========
Description
===========



Does the following:

 

 
* Adds new ``Attributes`` , ``Rules`` , or ``ObjectTypes`` . 
 
* Updates existing ``Attributes`` , ``Rules`` , or ``ObjectTypes`` . 
 
* Deletes existing ``Attributes`` , ``Rules`` , or ``ObjectTypes`` . 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/UpdateFacet>`_


========
Synopsis
========

::

    update-facet
  --schema-arn <value>
  --name <value>
  [--attribute-updates <value>]
  [--object-type <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--schema-arn`` (string)


  The Amazon Resource Name (ARN) that is associated with the  Facet . For more information, see  arns .

  

``--name`` (string)


  The name of the facet.

  

``--attribute-updates`` (list)


  List of attributes that need to be updated in a given schema  Facet . Each attribute is followed by ``AttributeAction`` , which specifies the type of update operation to perform. 

  



JSON Syntax::

  [
    {
      "Attribute": {
        "Name": "string",
        "AttributeDefinition": {
          "Type": "STRING"|"BINARY"|"BOOLEAN"|"NUMBER"|"DATETIME",
          "DefaultValue": {
            "StringValue": "string",
            "BinaryValue": blob,
            "BooleanValue": true|false,
            "NumberValue": "string",
            "DatetimeValue": timestamp
          },
          "IsImmutable": true|false,
          "Rules": {"string": {
                "Type": "BINARY_LENGTH"|"NUMBER_COMPARISON"|"STRING_FROM_SET"|"STRING_LENGTH",
                "Parameters": {"string": "string"
                  ...}
              }
            ...}
        },
        "AttributeReference": {
          "TargetFacetName": "string",
          "TargetAttributeName": "string"
        },
        "RequiredBehavior": "REQUIRED_ALWAYS"|"NOT_REQUIRED"
      },
      "Action": "CREATE_OR_UPDATE"|"DELETE"
    }
    ...
  ]



``--object-type`` (string)


  The object type that is associated with the facet. See  CreateFacetRequest$ObjectType for more details.

  

  Possible values:

  
  *   ``NODE``

  
  *   ``LEAF_NODE``

  
  *   ``POLICY``

  
  *   ``INDEX``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

