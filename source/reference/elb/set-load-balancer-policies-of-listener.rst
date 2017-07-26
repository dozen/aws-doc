[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb set-load-balancer-policies-of-listener:


**************************************
set-load-balancer-policies-of-listener
**************************************



===========
Description
===========



Associates, updates, or disables a policy with a listener for the specified load balancer. You can associate multiple policies with a listener.



========
Synopsis
========

::

    set-load-balancer-policies-of-listener
  --load-balancer-name <value>
  --load-balancer-port <value>
  --policy-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--load-balancer-port`` (integer)


  The external port of the load balancer for the policy.

  

``--policy-names`` (list)


  The names of the policies. If the list is empty, the current policy is removed from the listener.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

