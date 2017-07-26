[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot create-thing:


************
create-thing
************



===========
Description
===========



Creates a thing record in the thing registry.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/CreateThing>`_


========
Synopsis
========

::

    create-thing
  --thing-name <value>
  [--thing-type-name <value>]
  [--attribute-payload <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--thing-name`` (string)


  The name of the thing to create.

  

``--thing-type-name`` (string)


  The name of the thing type associated with the new thing.

  

``--attribute-payload`` (structure)


  The attribute payload, which consists of up to three name/value pairs in a JSON document. For example:

   

   ``{\"attributes\":{\"string1\":\"string2\"}}``  

  



Shorthand Syntax::

    attributes={KeyName1=string,KeyName2=string},merge=boolean




JSON Syntax::

  {
    "attributes": {"string": "string"
      ...},
    "merge": true|false
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

thingName -> (string)

  

  The name of the new thing.

  

  

thingArn -> (string)

  

  The ARN of the new thing.

  

  

