[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift delete-scaling-policy:


*********************
delete-scaling-policy
*********************



===========
Description
===========



Deletes a fleet scaling policy. This action means that the policy is no longer in force and removes all record of it. To delete a scaling policy, specify both the scaling policy name and the fleet ID it is associated with.

 

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
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/DeleteScalingPolicy>`_


========
Synopsis
========

::

    delete-scaling-policy
  --name <value>
  --fleet-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  Descriptive label that is associated with a scaling policy. Policy names do not need to be unique.

  

``--fleet-id`` (string)


  Unique identifier for a fleet to be deleted.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None