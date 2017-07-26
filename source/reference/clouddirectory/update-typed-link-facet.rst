[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory update-typed-link-facet:


***********************
update-typed-link-facet
***********************



===========
Description
===========



Updates a  TypedLinkFacet . For more information, see `Typed link <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/objectsandlinks.html#typedlink>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/UpdateTypedLinkFacet>`_


========
Synopsis
========

::

    update-typed-link-facet
  --schema-arn <value>
  --name <value>
  --attribute-updates <value>
  --identity-attribute-order <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--schema-arn`` (string)


  The Amazon Resource Name (ARN) that is associated with the schema. For more information, see  arns .

  

``--name`` (string)


  The unique name of the typed link facet.

  

``--attribute-updates`` (list)


  Attributes update structure.

  



Shorthand Syntax::

    Attribute={Name=string,Type=string,DefaultValue={StringValue=string,BinaryValue=blob,BooleanValue=boolean,NumberValue=string,DatetimeValue=timestamp},IsImmutable=boolean,Rules={KeyName1={Type=string,Parameters={KeyName1=string,KeyName2=string}},KeyName2={Type=string,Parameters={KeyName1=string,KeyName2=string}}},RequiredBehavior=string},Action=string ...




JSON Syntax::

  [
    {
      "Attribute": {
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
      },
      "Action": "CREATE_OR_UPDATE"|"DELETE"
    }
    ...
  ]



``--identity-attribute-order`` (list)


  The order of identity attributes for the facet, from most significant to least significant. The ability to filter typed links considers the order that the attributes are defined on the typed link facet. When providing ranges to a typed link selection, any inexact ranges must be specified at the end. Any attributes that do not have a range specified are presumed to match the entire range. Filters are interpreted in the order of the attributes on the typed link facet, not the order in which they are supplied to any API calls. For more information about identity attributes, see `Typed link <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/objectsandlinks.html#typedlink>`_ .

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

