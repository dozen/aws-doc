[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs test-metric-filter:


******************
test-metric-filter
******************



===========
Description
===========



Tests the filter pattern of a metric filter against a sample of log event messages. You can use this operation to validate the correctness of a metric filter pattern.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/TestMetricFilter>`_


========
Synopsis
========

::

    test-metric-filter
  --filter-pattern <value>
  --log-event-messages <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filter-pattern`` (string)


  A symbolic description of how CloudWatch Logs should interpret the data in each log event. For example, a log event may contain timestamps, IP addresses, strings, and so on. You use the filter pattern to specify what to look for in the log event message.

  

``--log-event-messages`` (list)


  The log event messages to test.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

matches -> (list)

  

  The matched events.

  

  (structure)

    

    Represents a matched event.

    

    eventNumber -> (long)

      

      The event number.

      

      

    eventMessage -> (string)

      

      The raw event data.

      

      

    extractedValues -> (map)

      

      The values extracted from the event data by the filter.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    

  

