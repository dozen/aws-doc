[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-load-balancers:


***********************
describe-load-balancers
***********************



===========
Description
===========



Describes the load balancers for the specified Auto Scaling group.



========
Synopsis
========

::

    describe-load-balancers
  --auto-scaling-group-name <value>
  [--next-token <value>]
  [--max-records <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the group.

  

``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a previous call.)

  

``--max-records`` (integer)


  The maximum number of items to return with this call.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe the load balancers for an Auto Scaling group**

This example describes the load balancers for the specified Auto Scaling group::

	aws autoscaling describe-load-balancers --auto-scaling-group-name my-auto-scaling-group

The following is example output::

  {
    "LoadBalancers": [
      {
        "State": "Added",
        "LoadBalancerName": "my-load-balancer"
      }
    ]
  }


======
Output
======

LoadBalancers -> (list)

  

  The load balancers.

  

  (structure)

    

    Describes the state of a load balancer.

    

    LoadBalancerName -> (string)

      

      The name of the load balancer.

      

      

    State -> (string)

      

      One of the following load balancer states:

       

       
      * ``Adding`` - The instances in the group are being registered with the load balancer.
       
      * ``Added`` - All instances in the group are registered with the load balancer.
       
      * ``InService`` - At least one instance in the group passed an ELB health check.
       
      * ``Removing`` - The instances are being deregistered from the load balancer. If connection draining is enabled, Elastic Load Balancing waits for in-flight requests to complete before deregistering the instances.
       

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

