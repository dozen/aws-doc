[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb create-app-cookie-stickiness-policy:


***********************************
create-app-cookie-stickiness-policy
***********************************



===========
Description
===========



Generates a stickiness policy with sticky session lifetimes that follow that of an application-generated cookie. This policy can be associated only with HTTP/HTTPS listeners.

 

This policy is similar to the policy created by  create-lb-cookie-stickiness-policy , except that the lifetime of the special Elastic Load Balancing cookie, ``AWSELB`` , follows the lifetime of the application-generated cookie specified in the policy configuration. The load balancer only inserts a new stickiness cookie when the application response includes a new application cookie.

 

If the application cookie is explicitly removed or expires, the session stops being sticky until a new application cookie is issued.

 

For more information, see `Application-Controlled Session Stickiness`_ in the *Elastic Load Balancing Developer Guide* .



========
Synopsis
========

::

    create-app-cookie-stickiness-policy
  --load-balancer-name <value>
  --policy-name <value>
  --cookie-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--policy-name`` (string)


  The name of the policy being created. Policy names must consist of alphanumeric characters and dashes (-). This name must be unique within the set of policies for this load balancer.

  

``--cookie-name`` (string)


  The name of the application cookie used for stickiness.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To generate a stickiness policy for your HTTPS load balancer**

This example generates a stickiness policy that follows the sticky session lifetimes of the application-generated cookie.

Command::

    aws elb create-app-cookie-stickiness-policy --load-balancer-name my-load-balancer --policy-name my-app-cookie-policy --cookie-name my-app-cookie


======
Output
======



.. _Application-Controlled Session Stickiness: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/elb-sticky-sessions.html#enable-sticky-sessions-application
