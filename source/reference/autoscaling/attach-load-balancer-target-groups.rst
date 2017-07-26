[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling attach-load-balancer-target-groups:


**********************************
attach-load-balancer-target-groups
**********************************



===========
Description
===========



Attaches one or more target groups to the specified Auto Scaling group.

 

To describe the target groups for an Auto Scaling group, use  describe-load-balancer-target-groups . To detach the target group from the Auto Scaling group, use  detach-load-balancer-target-groups .

 

For more information, see `Attach a Load Balancer to Your Auto Scaling Group <http://docs.aws.amazon.com/autoscaling/latest/userguide/attach-load-balancer-asg.html>`_ in the *Auto Scaling User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/AttachLoadBalancerTargetGroups>`_


========
Synopsis
========

::

    attach-load-balancer-target-groups
  --auto-scaling-group-name <value>
  --target-group-arns <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the Auto Scaling group.

  

``--target-group-arns`` (list)


  The Amazon Resource Names (ARN) of the target groups.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To attach a target group to an Auto Scaling group**

This example attaches the specified target group to the specified Auto Scaling group::

    aws autoscaling attach-load-balancer-target-groups --auto-scaling-group-name my-auto-scaling-group --target-group-arns arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-targets/73e2d6bc24d8a067


======
Output
======

