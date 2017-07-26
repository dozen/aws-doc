[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot create-thing-type:


*****************
create-thing-type
*****************



===========
Description
===========



Creates a new thing type.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/CreateThingType>`_


========
Synopsis
========

::

    create-thing-type
  --thing-type-name <value>
  [--thing-type-properties <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--thing-type-name`` (string)


  The name of the thing type.

  

``--thing-type-properties`` (structure)


  The thing-type-properties for the thing type to create. It contains information about the new thing type including a description, and a list of searchable thing attribute names.

  



Shorthand Syntax::

    thingTypeDescription=string,searchableAttributes=string,string




JSON Syntax::

  {
    "thingTypeDescription": "string",
    "searchableAttributes": ["string", ...]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

thingTypeName -> (string)

  

  The name of the thing type.

  

  

thingTypeArn -> (string)

  

  The Amazon Resource Name (ARN) of the thing type.

  

  

