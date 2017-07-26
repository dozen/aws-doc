[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb detach-load-balancer-from-subnets:


*********************************
detach-load-balancer-from-subnets
*********************************



===========
Description
===========



Removes the specified subnets from the set of configured subnets for the load balancer.

 

After a subnet is removed, all EC2 instances registered with the load balancer in the removed subnet go into the ``OutOfService`` state. Then, the load balancer balances the traffic among the remaining routable subnets.



========
Synopsis
========

::

    detach-load-balancer-from-subnets
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


  The IDs of the subnets.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To detach load balancers from subnets**

This example detaches the specified load balancer from the specified subnet.

Command::

     aws elb detach-load-balancer-from-subnets --load-balancer-name my-load-balancer --subnets subnet-0ecac448

Output::

   {
      "Subnets": [
          "subnet-15aaab61"
      ]
   }



======
Output
======

Subnets -> (list)

  

  The IDs of the remaining subnets for the load balancer.

  

  (string)

    

    

  

