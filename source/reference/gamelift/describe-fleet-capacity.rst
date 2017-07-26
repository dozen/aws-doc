[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-fleet-capacity:


***********************
describe-fleet-capacity
***********************



===========
Description
===========



Retrieves the current status of fleet capacity for one or more fleets. This information includes the number of instances that have been requested for the fleet and the number currently active. You can request capacity for all fleets, or specify a list of one or more fleet IDs. When requesting multiple fleets, use the pagination parameters to retrieve results as a set of sequential pages. If successful, a  FleetCapacity object is returned for each requested fleet ID. When specifying a list of fleet IDs, attribute objects are returned only for fleets that currently exist. 

 

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
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/DescribeFleetCapacity>`_


========
Synopsis
========

::

    describe-fleet-capacity
  [--fleet-ids <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--fleet-ids`` (list)


  Unique identifier for a fleet(s) to retrieve capacity information for. To request capacity information for all fleets, leave this parameter empty.

  



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

FleetCapacity -> (list)

  

  Collection of objects containing capacity information for each requested fleet ID. Leave this parameter empty to retrieve capacity information for all fleets.

  

  (structure)

    

    Information about the fleet's capacity. Fleet capacity is measured in EC2 instances. By default, new fleets have a capacity of one instance, but can be updated as needed. The maximum number of instances for a fleet is determined by the fleet's instance type.

     

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

      

      

    InstanceType -> (string)

      

      Name of an EC2 instance type that is supported in Amazon GameLift. A fleet instance type determines the computing resources of each instance in the fleet, including CPU, memory, storage, and networking capacity. Amazon GameLift supports the following EC2 instance types. See `Amazon EC2 Instance Types <http://aws.amazon.com/ec2/instance-types/>`_ for detailed descriptions.

      

      

    InstanceCounts -> (structure)

      

      Current status of fleet capacity.

      

      DESIRED -> (integer)

        

        Ideal number of active instances in the fleet.

        

        

      MINIMUM -> (integer)

        

        Minimum value allowed for the fleet's instance count.

        

        

      MAXIMUM -> (integer)

        

        Maximum value allowed for the fleet's instance count.

        

        

      PENDING -> (integer)

        

        Number of instances in the fleet that are starting but not yet active.

        

        

      ACTIVE -> (integer)

        

        Actual number of active instances in the fleet.

        

        

      IDLE -> (integer)

        

        Number of active instances in the fleet that are not currently hosting a game session.

        

        

      TERMINATING -> (integer)

        

        Number of instances in the fleet that are no longer active but haven't yet been terminated.

        

        

      

    

  

NextToken -> (string)

  

  Token that indicates where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

  

  

