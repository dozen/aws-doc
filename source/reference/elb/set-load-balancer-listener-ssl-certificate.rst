[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb set-load-balancer-listener-ssl-certificate:


******************************************
set-load-balancer-listener-ssl-certificate
******************************************



===========
Description
===========



Sets the certificate that terminates the specified listener's SSL connections. The specified certificate replaces any prior certificate that was used on the same load balancer and port.

 

For more information about updating your SSL certificate, see `Updating an SSL Certificate for a Load Balancer`_ in the *Elastic Load Balancing Developer Guide* .



========
Synopsis
========

::

    set-load-balancer-listener-ssl-certificate
  --load-balancer-name <value>
  --load-balancer-port <value>
  --ssl-certificate-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--load-balancer-port`` (integer)


  The port that uses the specified SSL certificate.

  

``--ssl-certificate-id`` (string)


  The Amazon Resource Name (ARN) of the SSL certificate.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To update the SSL certificate for an HTTPS load balancer**

This example replaces the existing SSL certificate for the specified HTTPS load balancer.

Command::

    aws elb set-load-balancer-listener-ssl-certificate --load-balancer-name my-load-balancer --load-balancer-port 443 --ssl-certificate-id arn:aws:iam::123456789012:server-certificate/new-server-cert



======
Output
======



.. _Updating an SSL Certificate for a Load Balancer: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/US_UpdatingLoadBalancerSSL.html
