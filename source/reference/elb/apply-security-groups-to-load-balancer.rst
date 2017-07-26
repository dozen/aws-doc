[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb apply-security-groups-to-load-balancer:


**************************************
apply-security-groups-to-load-balancer
**************************************



===========
Description
===========



Associates one or more security groups with your load balancer in a virtual private cloud (VPC). The specified security groups override the previously associated security groups.

 

For more information, see `Security Groups for Load Balancers in a VPC <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-security-groups.html#elb-vpc-security-groups>`_ in the *Classic Load Balancer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/ApplySecurityGroupsToLoadBalancer>`_


========
Synopsis
========

::

    apply-security-groups-to-load-balancer
  --load-balancer-name <value>
  --security-groups <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    

  

