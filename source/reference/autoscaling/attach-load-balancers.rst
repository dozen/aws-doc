[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling attach-load-balancers:


*********************
attach-load-balancers
*********************



===========
Description
===========



Attaches one or more load balancers to the specified Auto Scaling group.

 

To describe the load balancers for an Auto Scaling group, use  describe-load-balancers . To detach the load balancer from the Auto Scaling group, use  detach-load-balancers .

 

For more information, see `Attach a Load Balancer to Your Auto Scaling Group`_ in the *Auto Scaling Developer Guide* .



========
Synopsis
========

::

    attach-load-balancers
  [--auto-scaling-group-name <value>]
  [--load-balancer-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To attach a load balancer to an Auto Scaling group**

This example attaches the specified load balancer to the specified Auto Scaling group::

    aws autoscaling attach-load-balancers --load-balancer-names my-load-balancer --auto-scaling-group-name my-auto-scaling-group


======
Output
======



.. _Attach a Load Balancer to Your Auto Scaling Group: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/attach-load-balancer-asg.html
