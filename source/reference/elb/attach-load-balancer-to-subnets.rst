[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb attach-load-balancer-to-subnets:


*******************************
attach-load-balancer-to-subnets
*******************************



===========
Description
===========



Adds one or more subnets to the set of configured subnets for the specified load balancer.

 

The load balancer evenly distributes requests across all registered subnets. For more information, see `Add or Remove subnets for Your Load Balancer in a VPC`_ in the *Elastic Load Balancing Developer Guide* .



========
Synopsis
========

::

    attach-load-balancer-to-subnets
  --load-balancer-name <value>
  --subnets <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--subnets`` (list)


  The IDs of the subnets to add for the load balancer. You can add only one subnet per Availability Zone.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To attach subnets to a load balancer**

This example adds the specified subnet to the set of configured subnets for the specified load balancer.

Command::

  aws elb attach-load-balancer-to-subnets --load-balancer-name my-load-balancer --subnets subnet-0ecac448

Output::

   {
      "Subnets": [
          "subnet-15aaab61",
          "subnet-0ecac448"
      ]
   }



======
Output
======

Subnets -> (list)

  

  The IDs of the subnets attached to the load balancer.

  

  (string)

    

    

  



.. _Add or Remove subnets for Your Load Balancer in a VPC: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/elb-manage-subnets.html
