[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory add-facet-to-object:


*******************
add-facet-to-object
*******************



===========
Description
===========



Adds a new  Facet to an object.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/AddFacetToObject>`_


========
Synopsis
========

::

    add-facet-to-object
  --directory-arn <value>
  --schema-facet <value>
  [--object-attribute-list <value>]
  --object-reference <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  The Amazon Resource Name (ARN) that is associated with the  Directory where the object resides. For more information, see  arns .

  

``--schema-facet`` (structure)


  Identifiers for the facet that you are adding to the object.

  



Shorthand Syntax::

    SchemaArn=string,FacetName=string




JSON Syntax::

  {
    "SchemaArn": "string",
    "FacetName": "string"
  }



``--object-attribute-list`` (list)


  Attributes on the facet that you are adding to the object.

  



Shorthand Syntax::

    Key={SchemaArn=string,FacetName=string,Name=string},Value={StringValue=string,BinaryValue=blob,BooleanValue=boolean,NumberValue=string,DatetimeValue=timestamp} ...




JSON Syntax::

  [
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
  ]



``--object-reference`` (structure)


  A reference to the object you are adding the specified facet to.

  



Shorthand Syntax::

    Selector=string




JSON Syntax::

  {
    "Selector": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

