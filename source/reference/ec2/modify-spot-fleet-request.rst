[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-spot-fleet-request:


*************************
modify-spot-fleet-request
*************************



===========
Description
===========



Modifies the specified Spot fleet request.

 

While the Spot fleet request is being modified, it is in the ``modifying`` state.

 

To scale up your Spot fleet, increase its target capacity. The Spot fleet launches the additional Spot instances according to the allocation strategy for the Spot fleet request. If the allocation strategy is ``lowestPrice`` , the Spot fleet launches instances using the Spot pool with the lowest price. If the allocation strategy is ``diversified`` , the Spot fleet distributes the instances across the Spot pools.

 

To scale down your Spot fleet, decrease its target capacity. First, the Spot fleet cancels any open bids that exceed the new target capacity. You can request that the Spot fleet terminate Spot instances until the size of the fleet no longer exceeds the new target capacity. If the allocation strategy is ``lowestPrice`` , the Spot fleet terminates the instances with the highest price per unit. If the allocation strategy is ``diversified`` , the Spot fleet terminates instances across the Spot pools. Alternatively, you can request that the Spot fleet keep the fleet at its current size, but not replace any Spot instances that are interrupted or that you terminate manually.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ModifySpotFleetRequest>`_


========
Synopsis
========

::

    modify-spot-fleet-request
  [--excess-capacity-termination-policy <value>]
  --spot-fleet-request-id <value>
  [--target-capacity <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--excess-capacity-termination-policy`` (string)


  Indicates whether running Spot instances should be terminated if the target capacity of the Spot fleet request is decreased below the current size of the Spot fleet.

  

  Possible values:

  
  *   ``noTermination``

  
  *   ``default``

  

  

``--spot-fleet-request-id`` (string)


  The ID of the Spot fleet request.

  

``--target-capacity`` (integer)


  The size of the fleet.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To modify a Spot fleet request**

This example command updates the target capacity of the specified Spot fleet request.

Command::

  aws ec2 modify-spot-fleet-request --target-capacity 20 --spot-fleet-request-id sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE 

Output::

  {
      "Return": true
  }

This example command decreases the target capacity of the specified Spot fleet request without terminating any Spot Instances as a result.

Command::

  aws ec2 modify-spot-fleet-request --target-capacity 10 --excess-capacity-termination-policy NoTermination --spot-fleet-request-ids sfr-73fbd2ce-aa30-494c-8788-1cee4EXAMPLE

Output::

  {
      "Return": true
  }


======
Output
======

Return -> (boolean)

  

  Is ``true`` if the request succeeds, and an error otherwise.

  

  

