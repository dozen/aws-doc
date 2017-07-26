[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory create-typed-link-facet:


***********************
create-typed-link-facet
***********************



===========
Description
===========



Creates a  facet . For more information, see `Typed link <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/objectsandlinks.html#typedlink>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/CreateTypedLinkFacet>`_


========
Synopsis
========

::

    create-typed-link-facet
  --schema-arn <value>
  --facet <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--schema-arn`` (string)


  The Amazon Resource Name (ARN) that is associated with the schema. For more information, see  arns .

  

``--facet`` (structure)


    Facet structure that is associated with the typed link facet.

  



JSON Syntax::

  {
    "Name": "string",
    "Attributes": [
      {
        "Name": "string",
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
          ...},
        "RequiredBehavior": "REQUIRED_ALWAYS"|"NOT_REQUIRED"
      }
      ...
    ],
    "IdentityAttributeOrder": ["string", ...]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

