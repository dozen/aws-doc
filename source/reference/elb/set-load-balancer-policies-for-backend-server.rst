[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb set-load-balancer-policies-for-backend-server:


*********************************************
set-load-balancer-policies-for-backend-server
*********************************************



===========
Description
===========



Replaces the set of policies associated with the specified port on which the EC2 instance is listening with a new set of policies. At this time, only the back-end server authentication policy type can be applied to the instance ports; this policy type is composed of multiple public key policies.

 

Each time you use ``set-load-balancer-policies-for-backend-server`` to enable the policies, use the ``policy-names`` parameter to list the policies that you want to enable.

 

You can use  describe-load-balancers or  describe-load-balancer-policies to verify that the policy is associated with the EC2 instance.

 

For more information about enabling back-end instance authentication, see `Configure Back-end Instance Authentication <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-create-https-ssl-load-balancer.html#configure_backendauth_clt>`_ in the *Classic Load Balancer Guide* . For more information about Proxy Protocol, see `Configure Proxy Protocol Support <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/enable-proxy-protocol.html>`_ in the *Classic Load Balancer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/SetLoadBalancerPoliciesForBackendServer>`_


========
Synopsis
========

::

    set-load-balancer-policies-for-backend-server
  --load-balancer-name <value>
  --instance-port <value>
  --policy-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--instance-port`` (integer)


  The port number associated with the EC2 instance.

  

``--policy-names`` (list)


  The names of the policies. If the list is empty, then all current polices are removed from the EC2 instance.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To replace the policies associated with a port for a backend instance**

This example replaces the policies that are currently associated with the specified port.

Command::

  aws elb set-load-balancer-policies-for-backend-server --load-balancer-name my-load-balancer --instance-port 80 --policy-names my-ProxyProtocol-policy


**To remove all policies that are currently associated with a port on your backend instance**

This example removes all policies associated with the specified port.

Command::

  aws elb set-load-balancer-policies-for-backend-server --load-balancer-name my-load-balancer --instance-port 80 --policy-names []


To confirm that the policies are removed, use the ``describe-load-balancer-policies`` command.



======
Output
======

