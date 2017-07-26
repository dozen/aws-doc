[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 set-ip-address-type:


*******************
set-ip-address-type
*******************



===========
Description
===========



Sets the type of IP addresses used by the subnets of the specified Application Load Balancer.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/SetIpAddressType>`_


========
Synopsis
========

::

    set-ip-address-type
  --load-balancer-arn <value>
  --ip-address-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-arn`` (string)


  The Amazon Resource Name (ARN) of the load balancer.

  

``--ip-address-type`` (string)


  The IP address type. The possible values are ``ipv4`` (for IPv4 addresses) and ``dualstack`` (for IPv4 and IPv6 addresses). Internal load balancers must use ``ipv4`` .

  

  Possible values:

  
  *   ``ipv4``

  
  *   ``dualstack``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IpAddressType -> (string)

  

  The IP address type.

  

  

