[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 set-security-groups:


*******************
set-security-groups
*******************



===========
Description
===========



Associates the specified security groups with the specified load balancer. The specified security groups override the previously associated security groups.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/SetSecurityGroups>`_


========
Synopsis
========

::

    set-security-groups
  --load-balancer-arn <value>
  --security-groups <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-arn`` (string)


  The Amazon Resource Name (ARN) of the load balancer.

  

``--security-groups`` (list)


  The IDs of the security groups.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To associate a security group with a load balancer**

This example associates the specified security group with the specified load balancer.

Command::

  aws elbv2 set-security-groups --load-balancer-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188 --security-groups sg-5943793c

Output::

  {
    "SecurityGroupIds": [
        "sg-5943793c"
    ]
  }


======
Output
======

SecurityGroupIds -> (list)

  

  The IDs of the security groups associated with the load balancer.

  

  (string)

    

    

  

