[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling detach-load-balancers:


*********************
detach-load-balancers
*********************



===========
Description
===========



Removes one or more load balancers from the specified Auto Scaling group.

 

When you detach a load balancer, it enters the ``Removing`` state while deregistering the instances in the group. When all instances are deregistered, then you can no longer describe the load balancer using  describe-load-balancers . Note that the instances remain running.



========
Synopsis
========

::

    detach-load-balancers
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

**To detach a load balancer from an Auto Scaling group**

This example detaches the specified load balancer from the specified Auto Scaling group::

   aws autoscaling detach-load-balancers --load-balancer-names my-load-balancer --auto-scaling-group-name my-auto-scaling-group


======
Output
======

