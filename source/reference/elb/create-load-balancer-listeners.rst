[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb create-load-balancer-listeners:


******************************
create-load-balancer-listeners
******************************



===========
Description
===========



Creates one or more listeners for the specified load balancer. If a listener with the specified port does not already exist, it is created; otherwise, the properties of the new listener must match the properties of the existing listener.

 

For more information, see `Add a Listener to Your Load Balancer`_ in the *Elastic Load Balancing Developer Guide* .



========
Synopsis
========

::

    create-load-balancer-listeners
  --load-balancer-name <value>
  --listeners <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create listeners for a load balancer**

This example creates a listener for your load balancer at port 80 using the HTTP protocol.

Command::

     aws elb create-load-balancer-listeners --load-balancer-name my-load-balancer --listeners "Protocol=HTTP,LoadBalancerPort=80,InstanceProtocol=HTTP,InstancePort=80"



======
Output
======



.. _Add a Listener to Your Load Balancer: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/us-add-listener.html
