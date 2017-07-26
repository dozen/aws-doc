[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb apply-security-groups-to-load-balancer:


**************************************
apply-security-groups-to-load-balancer
**************************************



===========
Description
===========



Associates one or more security groups with your load balancer in a virtual private cloud (VPC). The specified security groups override the previously associated security groups.

 

For more information, see `Security Groups for Load Balancers in a VPC`_ in the *Elastic Load Balancing Developer Guide* .



========
Synopsis
========

::

    apply-security-groups-to-load-balancer
  --load-balancer-name <value>
  --security-groups <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--security-groups`` (list)


  The IDs of the security groups to associate with the load balancer. Note that you cannot specify the name of the security group.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To associate a security group with a load balancer in a VPC**

This example associates a security group with the specified load balancer in a VPC.

Command::

   aws elb apply-security-groups-to-load-balancer --load-balancer-name my-load-balancer --security-groups sg-fc448899

Output::

   {
     "SecurityGroups": [
         "sg-fc448899"
     ]
   }



======
Output
======

SecurityGroups -> (list)

  

  The IDs of the security groups associated with the load balancer.

  

  (string)

    

    

  



.. _Security Groups for Load Balancers in a VPC: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/elb-security-groups.html#elb-vpc-security-groups
