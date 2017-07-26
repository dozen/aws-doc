[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs test-metric-filter:


******************
test-metric-filter
******************



===========
Description
===========



Tests the filter pattern of a metric filter against a sample of log event messages. You can use this operation to validate the correctness of a metric filter pattern. 



========
Synopsis
========

::

    test-metric-filter
  --filter-pattern <value>
  --log-event-messages <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--filter-pattern`` (string)


  A symbolic description of how CloudWatch Logs should interpret the data in each log event. For example, a log event may contain timestamps, IP addresses, strings, and so on. You use the filter pattern to specify what to look for in the log event message.

  

``--log-event-messages`` (list)


  A list of log event messages to test.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

matches -> (list)

  

  (structure)

    

    eventNumber -> (long)

      

      

    eventMessage -> (string)

      

      

    extractedValues -> (map)

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    

  

