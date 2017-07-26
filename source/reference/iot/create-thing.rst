[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot create-thing:


************
create-thing
************



===========
Description
===========



Creates a thing in the thing registry.



========
Synopsis
========

::

    create-thing
  --thing-name <value>
  [--attribute-payload <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--thing-name`` (string)


  The name of the thing.

  

``--attribute-payload`` (structure)


  The attribute payload. Which consists of up to 3 name/value pairs in a JSON document. For example: {\"attributes\":{\"string1\":\"string2\"}}

  



Shorthand Syntax::

    attributes={KeyName1=string,KeyName2=string}




JSON Syntax::

  {
    "attributes": {"string": "string"
      ...}
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

thingName -> (string)

  

  The name of the thing.

  

  

thingArn -> (string)

  

  The thing ARN.

  

  

