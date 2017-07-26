[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-fleet-events:


*********************
describe-fleet-events
*********************



===========
Description
===========



Retrieves entries from the fleet event log. You can specify a time range to limit the result set. Use the pagination parameters to retrieve results as a set of sequential pages. If successful, a collection of event log entries matching the request are returned.



========
Synopsis
========

::

    describe-fleet-events
  --fleet-id <value>
  [--start-time <value>]
  [--end-time <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for the fleet to get event logs for. 

  

``--start-time`` (timestamp)


  Earliest date to retrieve event logs for. If no start time is specified, this call returns entries starting from when the fleet was created to the specified end time. Format is an integer representing the number of seconds since the Unix epoch (Unix time).

  

``--end-time`` (timestamp)


  Most recent date to retrieve event logs for. If no end time is specified, this call returns entries from the specified start time up to the present. Format is an integer representing the number of seconds since the Unix epoch (Unix time).

  

``--limit`` (integer)


  Maximum number of results to return. You can use this parameter with *NextToken* to get results as a set of sequential pages.

  

``--next-token`` (string)


  Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Events -> (list)

  

  Collection of objects containing event log entries for the specified fleet.

  

  (structure)

    

    Log entry describing an event involving an Amazon GameLift resource (such as a fleet).

    

    EventId -> (string)

      

      Unique identifier for a fleet event.

      

      

    ResourceId -> (string)

      

      Unique identifier for the resource, such as a fleet ID.

      

      

    EventCode -> (string)

      

      Type of event being logged.

      

      

    Message -> (string)

      

      Additional information related to the event.

      

      

    EventTime -> (timestamp)

      

      Time stamp indicating when this event occurred. Format is an integer representing the number of seconds since the Unix epoch (Unix time).

      

      

    

  

NextToken -> (string)

  

  Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

   

  .. note::

    

    If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

    

  

  

