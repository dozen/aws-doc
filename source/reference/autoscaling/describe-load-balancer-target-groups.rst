[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-load-balancer-target-groups:


************************************
describe-load-balancer-target-groups
************************************



===========
Description
===========



Describes the target groups for the specified Auto Scaling group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DescribeLoadBalancerTargetGroups>`_


========
Synopsis
========

::

    describe-load-balancer-target-groups
  --auto-scaling-group-name <value>
  [--next-token <value>]
  [--max-records <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the Auto Scaling group.

  

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

**To describe the target groups for an Auto Scaling group**

This example describes the target groups attached to the specified Auto Scaling group::

    aws autoscaling describe-load-balancer-target-groups --auto-scaling-group-name my-auto-scaling-group

The following is example output::

  {
    "LoadBalancerTargetGroups": [
        {
            "LoadBalancerTargetGroupARN": "arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-targets/73e2d6bc24d8a067",
            "State": "Added"
        }
    ]
  }


======
Output
======

LoadBalancerTargetGroups -> (list)

  

  Information about the target groups.

  

  (structure)

    

    Describes the state of a target group.

     

    If you attach a target group to an existing Auto Scaling group, the initial state is ``Adding`` . The state transitions to ``Added`` after all Auto Scaling instances are registered with the target group. If ELB health checks are enabled, the state transitions to ``InService`` after at least one Auto Scaling instance passes the health check. If EC2 health checks are enabled instead, the target group remains in the ``Added`` state.

    

    LoadBalancerTargetGroupARN -> (string)

      

      The Amazon Resource Name (ARN) of the target group.

      

      

    State -> (string)

      

      The state of the target group.

       

       
      * ``Adding`` - The Auto Scaling instances are being registered with the target group. 
       
      * ``Added`` - All Auto Scaling instances are registered with the target group. 
       
      * ``InService`` - At least one Auto Scaling instance passed an ELB health check. 
       
      * ``Removing`` - The Auto Scaling instances are being deregistered from the target group. If connection draining is enabled, Elastic Load Balancing waits for in-flight requests to complete before deregistering the instances. 
       
      * ``Removed`` - All Auto Scaling instances are deregistered from the target group. 
       

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

