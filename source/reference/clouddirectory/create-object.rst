[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory create-object:


*************
create-object
*************



===========
Description
===========



Creates an object in a  Directory . Additionally attaches the object to a parent, if a parent reference and ``link-name`` is specified. An object is simply a collection of  Facet attributes. You can also use this API call to create a policy object, if the facet from which you create the object is a policy facet. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/CreateObject>`_


========
Synopsis
========

::

    create-object
  --directory-arn <value>
  --schema-facets <value>
  [--object-attribute-list <value>]
  [--parent-reference <value>]
  [--link-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  The Amazon Resource Name (ARN) that is associated with the  Directory in which the object will be created. For more information, see  arns .

  

``--schema-facets`` (list)


  A list of schema facets to be associated with the object that contains ``SchemaArn`` and facet name. For more information, see  arns .

  



Shorthand Syntax::

    SchemaArn=string,FacetName=string ...




JSON Syntax::

  [
    {
      "SchemaArn": "string",
      "FacetName": "string"
    }
    ...
  ]



``--object-attribute-list`` (list)


  The attribute map whose attribute ARN contains the key and attribute value as the map value.

  



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



``--parent-reference`` (structure)


  If specified, the parent reference to which this object will be attached.

  



Shorthand Syntax::

    Selector=string




JSON Syntax::

  {
    "Selector": "string"
  }



``--link-name`` (string)


  The name of link that is used to attach this object to a parent.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ObjectIdentifier -> (string)

  

  The identifier that is associated with the object.

  

  

