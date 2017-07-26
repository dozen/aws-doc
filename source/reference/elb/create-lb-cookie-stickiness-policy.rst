[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb create-lb-cookie-stickiness-policy:


**********************************
create-lb-cookie-stickiness-policy
**********************************



===========
Description
===========



Generates a stickiness policy with sticky session lifetimes controlled by the lifetime of the browser (user-agent) or a specified expiration period. This policy can be associated only with HTTP/HTTPS listeners.

 

When a load balancer implements this policy, the load balancer uses a special cookie to track the back-end server instance for each request. When the load balancer receives a request, it first checks to see if this cookie is present in the request. If so, the load balancer sends the request to the application server specified in the cookie. If not, the load balancer sends the request to a server that is chosen based on the existing load-balancing algorithm.

 

A cookie is inserted into the response for binding subsequent requests from the same user to that server. The validity of the cookie is based on the cookie expiration time, which is specified in the policy configuration.

 

For more information, see `Duration-Based Session Stickiness`_ in the *Elastic Load Balancing Developer Guide* .



========
Synopsis
========

::

    create-lb-cookie-stickiness-policy
  --load-balancer-name <value>
  --policy-name <value>
  [--cookie-expiration-period <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--policy-name`` (string)


  The name of the policy being created. Policy names must consist of alphanumeric characters and dashes (-). This name must be unique within the set of policies for this load balancer.

  

``--cookie-expiration-period`` (long)


  The time period, in seconds, after which the cookie should be considered stale. If you do not specify this parameter, the sticky session lasts for the duration of the browser session.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To generate a duration-based stickiness policy for your HTTPS load balancer**

This example generates a stickiness policy with sticky session lifetimes controlled by the specified expiration period.


Command::

    aws elb create-lb-cookie-stickiness-policy --load-balancer-name my-load-balancer --policy-name my-duration-cookie-policy --cookie-expiration-period 60



======
Output
======



.. _Duration-Based Session Stickiness: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/elb-sticky-sessions.html#enable-sticky-sessions-duration
