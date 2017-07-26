[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot describe-thing:


**************
describe-thing
**************



===========
Description
===========



Gets information about the specified thing.



========
Synopsis
========

::

    describe-thing
  --thing-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--thing-name`` (string)


  The name of the thing.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

defaultClientId -> (string)

  

  The default client ID.

  

  

thingName -> (string)

  

  The name of the thing.

  

  

attributes -> (map)

  

  The attributes which are name/value pairs in JSON format. For example: 

   

  {\"attributes\":{\"some-name1\":\"some-value1\"}, {\"some-name2\":\"some-value2\"}, {\"some-name3\":\"some-value3\"}}

  

  key -> (string)

    

    

  value -> (string)

    

    

  

