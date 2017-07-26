[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 delete-load-balancer:


********************
delete-load-balancer
********************



===========
Description
===========



Deletes the specified Application Load Balancer and its attached listeners.

 

You can't delete a load balancer if deletion protection is enabled. If the load balancer does not exist or has already been deleted, the call succeeds.

 

Deleting a load balancer does not affect its registered targets. For example, your EC2 instances continue to run and are still registered to their target groups. If you no longer need these EC2 instances, you can stop or terminate them.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/DeleteLoadBalancer>`_


========
Synopsis
========

::

    delete-load-balancer
  --load-balancer-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-arn`` (string)


  The Amazon Resource Name (ARN) of the load balancer.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a load balancer**

This example deletes the specified load balancer.

Command::

  aws elbv2 delete-load-balancer --load-balancer-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188


======
Output
======

