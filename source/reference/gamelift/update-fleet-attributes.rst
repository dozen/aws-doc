[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift update-fleet-attributes:


***********************
update-fleet-attributes
***********************



===========
Description
===========



Updates fleet properties, including name and description, for a fleet. To update metadata, specify the fleet ID and the property values that you want to change. If successful, the fleet ID for the updated fleet is returned.

 

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
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/UpdateFleetAttributes>`_


========
Synopsis
========

::

    update-fleet-attributes
  --fleet-id <value>
  [--name <value>]
  [--description <value>]
  [--new-game-session-protection-policy <value>]
  [--resource-creation-limit-policy <value>]
  [--metric-groups <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for a fleet to update attribute metadata for.

  

``--name`` (string)


  Descriptive label that is associated with a fleet. Fleet names do not need to be unique.

  

``--description`` (string)


  Human-readable description of a fleet.

  

``--new-game-session-protection-policy`` (string)


  Game session protection policy to apply to all new instances created in this fleet. Instances that already exist are not affected. You can set protection for individual instances using  update-game-session .

   

   
  * **NoProtection** – The game session can be terminated during a scale-down event. 
   
  * **FullProtection** – If the game session is in an ``ACTIVE`` status, it cannot be terminated during a scale-down event. 
   

  

  Possible values:

  
  *   ``NoProtection``

  
  *   ``FullProtection``

  

  

``--resource-creation-limit-policy`` (structure)


  Policy that limits the number of game sessions an individual player can create over a span of time. 

  



Shorthand Syntax::

    NewGameSessionsPerCreator=integer,PolicyPeriodInMinutes=integer




JSON Syntax::

  {
    "NewGameSessionsPerCreator": integer,
    "PolicyPeriodInMinutes": integer
  }



``--metric-groups`` (list)


  Names of metric groups to include this fleet in. Amazon CloudWatch uses a fleet metric group is to aggregate metrics from multiple fleets. Use an existing metric group name to add this fleet to the group. Or use a new name to create a new metric group. A fleet can only be included in one metric group at a time.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FleetId -> (string)

  

  Unique identifier for a fleet that was updated.

  

  

