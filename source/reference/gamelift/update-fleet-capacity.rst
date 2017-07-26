[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift update-fleet-capacity:


*********************
update-fleet-capacity
*********************



===========
Description
===========



Updates capacity settings for a fleet. Use this action to specify the number of EC2 instances (hosts) you want this fleet to contain. Before calling this action, you may want to call  describe-ec2-instance-limits to get the maximum capacity based on the fleet's EC2 instance type.

 

To update fleet capacity, specify the fleet ID and the desired number of instances. If successful, Amazon GameLift starts or terminates instances so that the fleet's active instance count matches the desired instance count. You can view a fleet's current capacity information by calling  describe-fleet-capacity . If the desired instance count is higher than the instance type's limit, the "Limit Exceeded" exception will occur.



========
Synopsis
========

::

    update-fleet-capacity
  --fleet-id <value>
  --desired-instances <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for the fleet you want to update capacity for. 

  

``--desired-instances`` (integer)


  Number of EC2 instances you want this fleet to host.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

FleetId -> (string)

  

  Unique identifier for the updated fleet.

  

  

