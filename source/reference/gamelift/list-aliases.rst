[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift list-aliases:


************
list-aliases
************



===========
Description
===========



Retrieves a collection of alias records for this AWS account. You can filter the result set by alias name and/or routing strategy type. Use the pagination parameters to retrieve results in sequential pages. 

 

.. note::

  

  Aliases are not listed in any particular order.

  



========
Synopsis
========

::

    list-aliases
  [--routing-strategy-type <value>]
  [--name <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--routing-strategy-type`` (string)


  Type of routing to filter results on. Use this parameter to retrieve only aliases of a certain type. To retrieve all aliases, leave this parameter empty. Possible routing types include: 

  
  * SIMPLE: The alias resolves to one specific fleet. Use this type when routing to active fleets.
  
  * TERMINAL: The alias does not resolve to a fleet but instead can be used to display a message to the user. A terminal alias throws a TerminalRoutingStrategyException with the  RoutingStrategy message embedded.
  

  

  

  Possible values:

  
  *   ``SIMPLE``

  
  *   ``TERMINAL``

  

  

``--name`` (string)


  Descriptive label associated with this alias. Alias names do not need to be unique.

  

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

Aliases -> (list)

  

  Collection of alias records that match the list request. 

  

  (structure)

    

    Properties describing a fleet alias.

    

    AliasId -> (string)

      

      Unique identifier for a fleet alias.

      

      

    Name -> (string)

      

      Descriptive label associated with this alias. Alias names do not need to be unique.

      

      

    Description -> (string)

      

      Human-readable description of the alias.

      

      

    RoutingStrategy -> (structure)

      

      Routing configuration for a fleet alias. 

      

      Type -> (string)

        

        Type of routing strategy. Possible routing types include: 

        
        * SIMPLE: The alias resolves to one specific fleet. Use this type when routing to active fleets.
        
        * TERMINAL: The alias does not resolve to a fleet but instead can be used to display a message to the user. A terminal alias throws a TerminalRoutingStrategyException with the  RoutingStrategy message embedded.
        

        

        

        

      FleetId -> (string)

        

        Unique identifier for a fleet.

        

        

      Message -> (string)

        

        Message text to be used with a terminal routing strategy.

        

        

      

    CreationTime -> (timestamp)

      

      Time stamp indicating when this object was created. Format is an integer representing the number of seconds since the Unix epoch (Unix time).

      

      

    LastUpdatedTime -> (timestamp)

      

      Time stamp indicating when this object was last modified. Format is an integer representing the number of seconds since the Unix epoch (Unix time).

      

      

    

  

NextToken -> (string)

  

  Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

   

  .. note::

    

    If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

    

  

  

