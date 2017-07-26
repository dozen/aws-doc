[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot update-thing:


************
update-thing
************



===========
Description
===========



Updates the data for a thing.



========
Synopsis
========

::

    update-thing
  --thing-name <value>
  --attribute-payload <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--thing-name`` (string)


  The thing name.

  

``--attribute-payload`` (structure)


  The attribute payload, a JSON string containing up to three key-value pairs.

   

  For example: {\"attributes\":{\"string1\":\"string2\"}}

  



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

