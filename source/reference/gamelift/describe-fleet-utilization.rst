[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-fleet-utilization:


**************************
describe-fleet-utilization
**************************



===========
Description
===========



Retrieves utilization statistics for one or more fleets. You can request utilization data for all fleets, or specify a list of one or more fleet IDs. When requesting all fleets, use the pagination parameters to retrieve results as a set of sequential pages. If successful, a  FleetUtilization object is returned for each requested fleet ID. When specifying a list of fleet IDs, utilization objects are returned only for fleets that currently exist. 

 

.. note::

  

  Some API actions may limit the number of fleet IDs allowed in one request. If a request exceeds this limit, the request fails and the error message includes the maximum allowed.

  



========
Synopsis
========

::

    describe-fleet-utilization
  [--fleet-ids <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--fleet-ids`` (list)


  Unique identifier for the fleet(s) you want to retrieve utilization data for. Leave this parameter empty to retrieve utilization data for all fleets.

  



Syntax::

  "string" "string" ...



``--limit`` (integer)


  Maximum number of results to return. You can use this parameter with *NextToken* to get results as a set of sequential pages. This parameter is ignored when the request specifies one or a list of fleet IDs.

  

``--next-token`` (string)


  Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value. This parameter is ignored when the request specifies one or a list of fleet IDs.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

FleetUtilization -> (list)

  

  Collection of objects containing utilization information for each requested fleet ID.

  

  (structure)

    

    Current status of fleet utilization, including the number of game and player sessions being hosted.

    

    FleetId -> (string)

      

      Unique identifier for a fleet.

      

      

    ActiveGameSessionCount -> (integer)

      

      Number of active game sessions currently being hosted on fleet game servers.

      

      

    CurrentPlayerSessionCount -> (integer)

      

      Number of active player sessions currently being hosted on fleet game servers.

      

      

    MaximumPlayerSessionCount -> (integer)

      

      Maximum players allowed across all game sessions currently hosted in the fleet.

      

      

    

  

NextToken -> (string)

  

  Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

   

  .. note::

    

    If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

    

  

  

