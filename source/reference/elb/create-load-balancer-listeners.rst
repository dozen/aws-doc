[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb create-load-balancer-listeners:


******************************
create-load-balancer-listeners
******************************



===========
Description
===========



Creates one or more listeners for the specified load balancer. If a listener with the specified port does not already exist, it is created; otherwise, the properties of the new listener must match the properties of the existing listener.

 

For more information, see `listeners for Your Classic Load Balancer <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-listener-config.html>`_ in the *Classic Load Balancer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/CreateLoadBalancerListeners>`_


========
Synopsis
========

::

    create-load-balancer-listeners
  --load-balancer-name <value>
  --listeners <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--listeners`` (list)


  The listeners.

  



Shorthand Syntax::

    Protocol=string,LoadBalancerPort=integer,InstanceProtocol=string,InstancePort=integer,SSLCertificateId=string ...




JSON Syntax::

  [
    {
      "Protocol": "string",
      "LoadBalancerPort": integer,
      "InstanceProtocol": "string",
      "InstancePort": integer,
      "SSLCertificateId": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create HTTP listeners for a load balancer**

This example creates a listener for your load balancer at port 80 using the HTTP protocol.

Command::

     aws elb create-load-balancer-listeners --load-balancer-name my-load-balancer --listeners "Protocol=HTTP,LoadBalancerPort=80,InstanceProtocol=HTTP,InstancePort=80"

**To create HTTPS listeners for a load balancer**

This example creates a listener for your load balancer at port 443 using the HTTPS protocol.

Command::

     aws elb create-load-balancer-listeners --load-balancer-name my-load-balancer --listeners "Protocol=HTTPS,LoadBalancerPort=443,InstanceProtocol=HTTP,InstancePort=80"



======
Output
======

