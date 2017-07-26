[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling attach-load-balancers:


*********************
attach-load-balancers
*********************



===========
Description
===========



Attaches one or more Classic Load Balancers to the specified Auto Scaling group.

 

To attach an Application Load Balancer instead, see  attach-load-balancer-target-groups .

 

To describe the load balancers for an Auto Scaling group, use  describe-load-balancers . To detach the load balancer from the Auto Scaling group, use  detach-load-balancers .

 

For more information, see `Attach a Load Balancer to Your Auto Scaling Group <http://docs.aws.amazon.com/autoscaling/latest/userguide/attach-load-balancer-asg.html>`_ in the *Auto Scaling User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/AttachLoadBalancers>`_


========
Synopsis
========

::

    attach-load-balancers
  --auto-scaling-group-name <value>
  --load-balancer-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the group.

  

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

**To attach a load balancer to an Auto Scaling group**

This example attaches the specified load balancer to the specified Auto Scaling group::

    aws autoscaling attach-load-balancers --load-balancer-names my-load-balancer --auto-scaling-group-name my-auto-scaling-group


======
Output
======

