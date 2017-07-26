[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling detach-load-balancers:


*********************
detach-load-balancers
*********************



===========
Description
===========



Detaches one or more Classic Load Balancers from the specified Auto Scaling group.

 

Note that this operation detaches only Classic Load Balancers. If you have Application Load Balancers, use  detach-load-balancer-target-groups instead.

 

When you detach a load balancer, it enters the ``Removing`` state while deregistering the instances in the group. When all instances are deregistered, then you can no longer describe the load balancer using  describe-load-balancers . Note that the instances remain running.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DetachLoadBalancers>`_


========
Synopsis
========

::

    detach-load-balancers
  --auto-scaling-group-name <value>
  --load-balancer-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the Auto Scaling group.

  

``--load-balancer-names`` (list)


  One or more load balancer names.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To detach a load balancer from an Auto Scaling group**

This example detaches the specified load balancer from the specified Auto Scaling group::

    aws autoscaling detach-load-balancers --load-balancer-names my-load-balancer --auto-scaling-group-name my-auto-scaling-group


======
Output
======

