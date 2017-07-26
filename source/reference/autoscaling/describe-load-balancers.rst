[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-load-balancers:


***********************
describe-load-balancers
***********************



===========
Description
===========



Describes the load balancers for the specified Auto Scaling group.

 

Note that this operation describes only Classic Load Balancers. If you have Application Load Balancers, use  describe-load-balancer-target-groups instead.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DescribeLoadBalancers>`_


========
Synopsis
========

::

    describe-load-balancers
  --auto-scaling-group-name <value>
  [--next-token <value>]
  [--max-records <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the group.

  

``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a previous call.)

  

``--max-records`` (integer)


  The maximum number of items to return with this call. The default value is 50 and the maximum value is 100.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    Describes the state of a Classic Load Balancer.

     

    If you specify a load balancer when creating the Auto Scaling group, the state of the load balancer is ``InService`` .

     

    If you attach a load balancer to an existing Auto Scaling group, the initial state is ``Adding`` . The state transitions to ``Added`` after all instances in the group are registered with the load balancer. If ELB health checks are enabled for the load balancer, the state transitions to ``InService`` after at least one instance in the group passes the health check. If EC2 health checks are enabled instead, the load balancer remains in the ``Added`` state.

    

    LoadBalancerName -> (string)

      

      The name of the load balancer.

      

      

    State -> (string)

      

      One of the following load balancer states:

       

       
      * ``Adding`` - The instances in the group are being registered with the load balancer. 
       
      * ``Added`` - All instances in the group are registered with the load balancer. 
       
      * ``InService`` - At least one instance in the group passed an ELB health check. 
       
      * ``Removing`` - The instances in the group are being deregistered from the load balancer. If connection draining is enabled, Elastic Load Balancing waits for in-flight requests to complete before deregistering the instances. 
       
      * ``Removed`` - All instances in the group are deregistered from the load balancer. 
       

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

