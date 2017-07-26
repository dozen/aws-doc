[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb set-load-balancer-listener-ssl-certificate:


******************************************
set-load-balancer-listener-ssl-certificate
******************************************



===========
Description
===========



Sets the certificate that terminates the specified listener's SSL connections. The specified certificate replaces any prior certificate that was used on the same load balancer and port.

 

For more information about updating your SSL certificate, see `Replace the SSL Certificate for Your Load Balancer <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-update-ssl-cert.html>`_ in the *Classic Load Balancer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/SetLoadBalancerListenerSSLCertificate>`_


========
Synopsis
========

::

    set-load-balancer-listener-ssl-certificate
  --load-balancer-name <value>
  --load-balancer-port <value>
  --ssl-certificate-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

