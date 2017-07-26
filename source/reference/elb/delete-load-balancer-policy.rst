[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb delete-load-balancer-policy:


***************************
delete-load-balancer-policy
***************************



===========
Description
===========



Deletes the specified policy from the specified load balancer. This policy must not be enabled for any listeners.



========
Synopsis
========

::

    delete-load-balancer-policy
  --load-balancer-name <value>
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--policy-name`` (string)


  The name of the policy.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a policy from your load balancer**

This example deletes the specified policy from the specified load balancer. The policy must not be enabled on any listener.

Command::

      aws elb delete-load-balancer-policy --load-balancer-name my-load-balancer --policy-name my-duration-cookie-policy



======
Output
======

