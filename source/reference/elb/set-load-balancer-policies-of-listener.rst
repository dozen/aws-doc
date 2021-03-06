[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb set-load-balancer-policies-of-listener:


**************************************
set-load-balancer-policies-of-listener
**************************************



===========
Description
===========



Replaces the current set of policies for the specified load balancer port with the specified set of policies.

 

To enable back-end server authentication, use  set-load-balancer-policies-for-backend-server .

 

For more information about setting policies, see `Update the SSL Negotiation Configuration <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/ssl-config-update.html>`_ , `Duration-Based Session Stickiness <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-sticky-sessions.html#enable-sticky-sessions-duration>`_ , and `Application-Controlled Session Stickiness <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-sticky-sessions.html#enable-sticky-sessions-application>`_ in the *Classic Load Balancer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/SetLoadBalancerPoliciesOfListener>`_


========
Synopsis
========

::

    set-load-balancer-policies-of-listener
  --load-balancer-name <value>
  --load-balancer-port <value>
  --policy-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--load-balancer-port`` (integer)


  The external port of the load balancer.

  

``--policy-names`` (list)


  The names of the policies. This list must include all policies to be enabled. If you omit a policy that is currently enabled, it is disabled. If the list is empty, all current policies are disabled.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To replace the policies associated with a listener**

This example replaces the policies that are currently associated with the specified listener.

Command::

  aws elb set-load-balancer-policies-of-listener --load-balancer-name my-load-balancer --load-balancer-port 443 --policy-names my-SSLNegotiation-policy


**To remove all policies associated with your listener**

This example removes all policies that are currently associated with the specified listener.

Command::

  aws elb set-load-balancer-policies-of-listener --load-balancer-name my-load-balancer --load-balancer-port 443 --policy-names []

To confirm that the policies are removed from the load balancer, use the ``describe-load-balancer-policies`` command.



======
Output
======

