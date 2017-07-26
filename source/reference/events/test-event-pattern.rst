[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events test-event-pattern:


******************
test-event-pattern
******************



===========
Description
===========



Tests whether the specified event pattern matches the provided event.

 

Most services in AWS treat : or / as the same character in Amazon Resource Names (ARNs). However, CloudWatch Events uses an exact match in event patterns and rules. Be sure to use the correct ARN characters when creating event patterns so that they match the ARN syntax in the event you want to match.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/events-2015-10-07/TestEventPattern>`_


========
Synopsis
========

::

    test-event-pattern
  --event-pattern <value>
  --event <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--event-pattern`` (string)


  The event pattern. For more information, see `Events and Event Patterns <http://docs.aws.amazon.com/AmazonCloudWatch/latest/events/CloudWatchEventsandEventPatterns.html>`_ in the *Amazon CloudWatch Events User Guide* .

  

``--event`` (string)


  The event, in JSON format, to test against the event pattern.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To check whether an event pattern matches a specified event**

This example tests whether the pattern "source:com.mycompany.myapp" matches the specified event. In this example, the output would be "true"::

  aws events test-event-pattern --event-pattern "{\"source\":[\"com.mycompany.myapp\"]}" --event "{\"id\":\"1\",\"source\":\"com.mycompany.myapp\",\"detail-type\":\"myDetailType\",\"account\":\"123456789012\",\"region\":\"us-east-1\",\"time\":\"2017-04-11T20:11:04Z\"}"


======
Output
======

Result -> (boolean)

  

  Indicates whether the event matches the event pattern.

  

  

