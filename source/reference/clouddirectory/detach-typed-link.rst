[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory detach-typed-link:


*****************
detach-typed-link
*****************



===========
Description
===========



Detaches a typed link from a specified source and target object. For more information, see `Typed link <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/objectsandlinks.html#typedlink>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/DetachTypedLink>`_


========
Synopsis
========

::

    detach-typed-link
  --directory-arn <value>
  --typed-link-specifier <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  The Amazon Resource Name (ARN) of the directory where you want to detach the typed link.

  

``--typed-link-specifier`` (structure)


  Used to accept a typed link specifier as input.

  



JSON Syntax::

  {
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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None