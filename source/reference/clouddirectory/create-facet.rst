[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory create-facet:


************
create-facet
************



===========
Description
===========



Creates a new  Facet in a schema. Facet creation is allowed only in development or applied schemas.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/CreateFacet>`_


========
Synopsis
========

::

    create-facet
  --schema-arn <value>
  --name <value>
  [--attributes <value>]
  --object-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--schema-arn`` (string)


  The schema ARN in which the new  Facet will be created. For more information, see  arns .

  

``--name`` (string)


  The name of the  Facet , which is unique for a given schema.

  

``--attributes`` (list)


  The attributes that are associated with the  Facet .

  



Shorthand Syntax::

    Name=string,AttributeDefinition={Type=string,DefaultValue={StringValue=string,BinaryValue=blob,BooleanValue=boolean,NumberValue=string,DatetimeValue=timestamp},IsImmutable=boolean,Rules={KeyName1={Type=string,Parameters={KeyName1=string,KeyName2=string}},KeyName2={Type=string,Parameters={KeyName1=string,KeyName2=string}}}},AttributeReference={TargetFacetName=string,TargetAttributeName=string},RequiredBehavior=string ...




JSON Syntax::

  [
    {
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
    }
    ...
  ]



``--object-type`` (string)


  Specifies whether a given object created from this facet is of type node, leaf node, policy or index.

   

   
  * Node: Can have multiple children but one parent. 
   

   

   
  * Leaf node: Cannot have children but can have multiple parents. 
   

   

   
  * Policy: Allows you to store a policy document and policy type. For more information, see `Policies <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/cd_key_concepts.html#policies>`_ . 
   

   

   
  * Index: Can be created with the Index API. 
   

  

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

