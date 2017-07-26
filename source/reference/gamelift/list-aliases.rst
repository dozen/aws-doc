[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift list-aliases:


************
list-aliases
************



===========
Description
===========



Retrieves all aliases for this AWS account. You can filter the result set by alias name and/or routing strategy type. Use the pagination parameters to retrieve results in sequential pages.

 

.. note::

   

  Returned aliases are not listed in any particular order.

   

 

Alias-related operations include:

 

 
*  create-alias   
 
*  list-aliases   
 
*  describe-alias   
 
*  update-alias   
 
*  delete-alias   
 
*  resolve-alias   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/ListAliases>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--routing-strategy-type`` (string)


  Type of routing to filter results on. Use this parameter to retrieve only aliases of a certain type. To retrieve all aliases, leave this parameter empty.

   

  Possible routing types include the following:

   

   
  * **SIMPLE** – The alias resolves to one specific fleet. Use this type when routing to active fleets. 
   
  * **TERMINAL** – The alias does not resolve to a fleet but instead can be used to display a message to the user. A terminal alias throws a TerminalRoutingStrategyException with the  RoutingStrategy message embedded. 
   

  

  Possible values:

  
  *   ``SIMPLE``

  
  *   ``TERMINAL``

  

  

``--name`` (string)


  Descriptive label that is associated with an alias. Alias names do not need to be unique.

  

``--limit`` (integer)


  Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages.

  

``--next-token`` (string)


  Token that indicates the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Aliases -> (list)

  

  Collection of alias records that match the list request.

  

  (structure)

    

    Properties describing a fleet alias.

     

    Alias-related operations include:

     

     
    *  create-alias   
     
    *  list-aliases   
     
    *  describe-alias   
     
    *  update-alias   
     
    *  delete-alias   
     
    *  resolve-alias   
     

    

    AliasId -> (string)

      

      Unique identifier for an alias; alias IDs are unique within a region.

      

      

    Name -> (string)

      

      Descriptive label that is associated with an alias. Alias names do not need to be unique.

      

      

    AliasArn -> (string)

      

      Unique identifier for an alias; alias ARNs are unique across all regions.

      

      

    Description -> (string)

      

      Human-readable description of an alias.

      

      

    RoutingStrategy -> (structure)

      

      Alias configuration for the alias, including routing type and settings.

      

      Type -> (string)

        

        Type of routing strategy.

         

        Possible routing types include the following:

         

         
        * **SIMPLE** – The alias resolves to one specific fleet. Use this type when routing to active fleets. 
         
        * **TERMINAL** – The alias does not resolve to a fleet but instead can be used to display a message to the user. A terminal alias throws a TerminalRoutingStrategyException with the  RoutingStrategy message embedded. 
         

        

        

      FleetId -> (string)

        

        Unique identifier for a fleet that the alias points to.

        

        

      Message -> (string)

        

        Message text to be used with a terminal routing strategy.

        

        

      

    CreationTime -> (timestamp)

      

      Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (for example "1469498468.057").

      

      

    LastUpdatedTime -> (timestamp)

      

      Time stamp indicating when this data object was last modified. Format is a number expressed in Unix time as milliseconds (for example "1469498468.057").

      

      

    

  

NextToken -> (string)

  

  Token that indicates where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

  

  

