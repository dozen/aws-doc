[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory update-object-attributes:


************************
update-object-attributes
************************



===========
Description
===========



Updates a given object's attributes.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/UpdateObjectAttributes>`_


========
Synopsis
========

::

    update-object-attributes
  --directory-arn <value>
  --object-reference <value>
  --attribute-updates <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  The Amazon Resource Name (ARN) that is associated with the  Directory where the object resides. For more information, see  arns .

  

``--object-reference`` (structure)


  The reference that identifies the object.

  



Shorthand Syntax::

    Selector=string




JSON Syntax::

  {
    "Selector": "string"
  }



``--attribute-updates`` (list)


  The attributes update structure.

  



Shorthand Syntax::

    ObjectAttributeKey={SchemaArn=string,FacetName=string,Name=string},ObjectAttributeAction={ObjectAttributeActionType=string,ObjectAttributeUpdateValue={StringValue=string,BinaryValue=blob,BooleanValue=boolean,NumberValue=string,DatetimeValue=timestamp}} ...




JSON Syntax::

  [
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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ObjectIdentifier -> (string)

  

  The ``ObjectIdentifier`` of the updated object.

  

  

