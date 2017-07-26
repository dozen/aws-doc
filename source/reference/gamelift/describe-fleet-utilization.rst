[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-fleet-utilization:


**************************
describe-fleet-utilization
**************************



===========
Description
===========



Retrieves utilization statistics for one or more fleets. You can request utilization data for all fleets, or specify a list of one or more fleet IDs. When requesting multiple fleets, use the pagination parameters to retrieve results as a set of sequential pages. If successful, a  FleetUtilization object is returned for each requested fleet ID. When specifying a list of fleet IDs, utilization objects are returned only for fleets that currently exist. 

 

.. note::

   

  Some API actions may limit the number of fleet IDs allowed in one request. If a request exceeds this limit, the request fails and the error message includes the maximum allowed.

   

 

Fleet-related operations include:

 

 
*  create-fleet   
 
*  list-fleets   
 
* Describe fleets: 

   
  *  describe-fleet-attributes   
   
  *  describe-fleet-port-settings   
   
  *  describe-fleet-utilization   
   
  *  describe-runtime-configuration   
   
  *  describe-fleet-events   
   

 
 
* Update fleets: 

   
  *  update-fleet-attributes   
   
  *  update-fleet-capacity   
   
  *  update-fleet-port-settings   
   
  *  update-runtime-configuration   
   

 
 
* Manage fleet capacity: 

   
  *  describe-fleet-capacity   
   
  *  update-fleet-capacity   
   
  *  put-scaling-policy (automatic scaling) 
   
  *  describe-scaling-policies (automatic scaling) 
   
  *  delete-scaling-policy (automatic scaling) 
   
  *  describe-ec2-instance-limits   
   

 
 
*  delete-fleet   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/DescribeFleetUtilization>`_


========
Synopsis
========

::

    describe-fleet-utilization
  [--fleet-ids <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--fleet-ids`` (list)


  Unique identifier for a fleet(s) to retrieve utilization data for. To request utilization data for all fleets, leave this parameter empty.

  



Syntax::

  "string" "string" ...



``--limit`` (integer)


  Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages. This parameter is ignored when the request specifies one or a list of fleet IDs.

  

``--next-token`` (string)


  Token that indicates the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value. This parameter is ignored when the request specifies one or a list of fleet IDs.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FleetUtilization -> (list)

  

  Collection of objects containing utilization information for each requested fleet ID.

  

  (structure)

    

    Current status of fleet utilization, including the number of game and player sessions being hosted.

     

    Fleet-related operations include:

     

     
    *  create-fleet   
     
    *  list-fleets   
     
    * Describe fleets: 

       
      *  describe-fleet-attributes   
       
      *  describe-fleet-port-settings   
       
      *  describe-fleet-utilization   
       
      *  describe-runtime-configuration   
       
      *  describe-fleet-events   
       

     
     
    * Update fleets: 

       
      *  update-fleet-attributes   
       
      *  update-fleet-capacity   
       
      *  update-fleet-port-settings   
       
      *  update-runtime-configuration   
       

     
     
    * Manage fleet capacity: 

       
      *  describe-fleet-capacity   
       
      *  update-fleet-capacity   
       
      *  put-scaling-policy (automatic scaling) 
       
      *  describe-scaling-policies (automatic scaling) 
       
      *  delete-scaling-policy (automatic scaling) 
       
      *  describe-ec2-instance-limits   
       

     
     
    *  delete-fleet   
     

    

    FleetId -> (string)

      

      Unique identifier for a fleet.

      

      

    ActiveServerProcessCount -> (integer)

      

      Number of server processes in an ``ACTIVE`` status currently running across all instances in the fleet

      

      

    ActiveGameSessionCount -> (integer)

      

      Number of active game sessions currently being hosted on all instances in the fleet.

      

      

    CurrentPlayerSessionCount -> (integer)

      

      Number of active player sessions currently being hosted on all instances in the fleet.

      

      

    MaximumPlayerSessionCount -> (integer)

      

      Maximum players allowed across all game sessions currently being hosted on all instances in the fleet.

      

      

    

  

NextToken -> (string)

  

  Token that indicates where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

  

  

