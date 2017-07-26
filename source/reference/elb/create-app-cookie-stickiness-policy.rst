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

 

For more information, see `Application-Controlled Session Stickiness <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-sticky-sessions.html#enable-sticky-sessions-application>`_ in the *Classic Load Balancer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/CreateAppCookieStickinessPolicy>`_


========
Synopsis
========

::

    create-app-cookie-stickiness-policy
  --load-balancer-name <value>
  --policy-name <value>
  --cookie-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

