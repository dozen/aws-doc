[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr modify-instance-fleet:


*********************
modify-instance-fleet
*********************



===========
Description
===========



Modifies the target On-Demand and target Spot capacities for the instance fleet with the specified InstanceFleetID within the cluster specified using ClusterID. The call either succeeds or fails atomically.

 

.. note::

   

  The instance fleet configuration is available only in Amazon EMR versions 4.8.0 and later, excluding 5.0.x versions.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticmapreduce-2009-03-31/ModifyInstanceFleet>`_


========
Synopsis
========

::

    modify-instance-fleet
  --cluster-id <value>
  --instance-fleet <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-id`` (string)


  The unique identifier of the cluster.

  

``--instance-fleet`` (structure)


  The unique identifier of the instance fleet.

  



Shorthand Syntax::

    InstanceFleetId=string,TargetOnDemandCapacity=integer,TargetSpotCapacity=integer




JSON Syntax::

  {
    "InstanceFleetId": "string",
    "TargetOnDemandCapacity": integer,
    "TargetSpotCapacity": integer
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To change the target capacites of an instance fleet**

This example changes the On-Demand and Spot target capacities to 1 for the instance fleet specified.

Command::

  aws emr modify-instance-fleet --cluster-id 'j-12ABCDEFGHI34JK' --instance-fleet InstanceFleetId='if-2ABC4DEFGHIJ4',TargetOnDemandCapacity=1,TargetSpotCapacity=1


======
Output
======

None