[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb attach-load-balancer-to-subnets:


*******************************
attach-load-balancer-to-subnets
*******************************



===========
Description
===========



Adds one or more subnets to the set of configured subnets for the specified load balancer.

 

The load balancer evenly distributes requests across all registered subnets. For more information, see `Add or Remove subnets for Your Load Balancer in a VPC <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-manage-subnets.html>`_ in the *Classic Load Balancer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/AttachLoadBalancerToSubnets>`_


========
Synopsis
========

::

    attach-load-balancer-to-subnets
  --load-balancer-name <value>
  --subnets <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--subnets`` (list)


  The IDs of the subnets to add. You can add only one subnet per Availability Zone.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    

  

