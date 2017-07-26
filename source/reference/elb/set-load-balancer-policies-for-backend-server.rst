[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb set-load-balancer-policies-for-backend-server:


*********************************************
set-load-balancer-policies-for-backend-server
*********************************************



===========
Description
===========



Replaces the set of policies associated with the specified port on which the back-end server is listening with a new set of policies. At this time, only the back-end server authentication policy type can be applied to the back-end ports; this policy type is composed of multiple public key policies.

 

Each time you use ``set-load-balancer-policies-for-backend-server`` to enable the policies, use the ``policy-names`` parameter to list the policies that you want to enable.

 

You can use  describe-load-balancers or  describe-load-balancer-policies to verify that the policy is associated with the back-end server.



========
Synopsis
========

::

    set-load-balancer-policies-for-backend-server
  --load-balancer-name <value>
  --instance-port <value>
  --policy-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--instance-port`` (integer)


  The port number associated with the back-end server.

  

``--policy-names`` (list)


  The names of the policies. If the list is empty, then all current polices are removed from the back-end server.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

