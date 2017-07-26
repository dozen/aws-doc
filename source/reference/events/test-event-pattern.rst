[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events test-event-pattern:


******************
test-event-pattern
******************



===========
Description
===========



Tests whether an event pattern matches the provided event.

 

 **Note:** Most services in AWS treat : or / as the same character in Amazon Resource Names (ARNs). However, CloudWatch Events uses an exact match in event patterns and rules. Be sure to use the correct ARN characters when creating event patterns so that they match the ARN syntax in the event you want to match. 



========
Synopsis
========

::

    test-event-pattern
  --event-pattern <value>
  --event <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--event-pattern`` (string)


  The event pattern you want to test.

  

``--event`` (string)


  The event in the JSON format to test against the event pattern.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Result -> (boolean)

  

  Indicates whether the event matches the event pattern.

  

  

