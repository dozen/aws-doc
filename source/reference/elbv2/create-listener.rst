[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 create-listener:


***************
create-listener
***************



===========
Description
===========



Creates a listener for the specified Application Load Balancer.

 

You can create up to 10 listeners per load balancer.

 

To update a listener, use  modify-listener . When you are finished with a listener, you can delete it using  delete-listener . If you are finished with both the listener and the load balancer, you can delete them both using  delete-load-balancer .

 

For more information, see `Listeners for Your Application Load Balancers <http://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-listeners.html>`_ in the *Application Load Balancers Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/CreateListener>`_


========
Synopsis
========

::

    create-listener
  --load-balancer-arn <value>
  --protocol <value>
  --port <value>
  [--ssl-policy <value>]
  [--certificates <value>]
  --default-actions <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-arn`` (string)


  The Amazon Resource Name (ARN) of the load balancer.

  

``--protocol`` (string)


  The protocol for connections from clients to the load balancer.

  

  Possible values:

  
  *   ``HTTP``

  
  *   ``HTTPS``

  

  

``--port`` (integer)


  The port on which the load balancer is listening.

  

``--ssl-policy`` (string)


  The security policy that defines which ciphers and protocols are supported. The default is the current predefined security policy.

  

``--certificates`` (list)


  The SSL server certificate. You must provide exactly one certificate if the protocol is HTTPS.

  



Shorthand Syntax::

    CertificateArn=string ...




JSON Syntax::

  [
    {
      "CertificateArn": "string"
    }
    ...
  ]



``--default-actions`` (list)


  The default action for the listener.

  



Shorthand Syntax::

    Type=string,TargetGroupArn=string ...




JSON Syntax::

  [
    {
      "Type": "forward",
      "TargetGroupArn": "string"
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

**To create an HTTP listener**

This example creates an HTTP listener for the specified load balancer that forwards requests to the specified target group.

Command::

  aws elbv2 create-listener --load-balancer-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188 --protocol HTTP --port 80 --default-actions Type=forward,TargetGroupArn=arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-targets/73e2d6bc24d8a067

Output::

  {
    "Listeners": [
        {
            "Protocol": "HTTP",
            "DefaultActions": [
                {
                    "TargetGroupArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-targets/73e2d6bc24d8a067",
                    "Type": "forward"
                }
            ],
            "LoadBalancerArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188",
            "Port": 80,
            "ListenerArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:listener/app/my-load-balancer/50dc6c495c0c9188/f2f7dc8efc522ab2"
        }
    ]
  }

**To create an HTTPS listener**

This example creates an HTTPS listener for the specified load balancer that forwards requests to the specified target group. Note that you must specify an SSL certificate for an HTTPS listener. You can create and manage certificates using AWS Certificate Manager (ACM). Alternatively, you can create a certificate using SSL/TLS tools, get the certificate signed by a certificate authority (CA), and upload the certificate to AWS Identity and Access Management (IAM).

Command::

  aws elbv2 create-listener --load-balancer-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188 --protocol HTTPS --port 443 --certificates CertificateArn=arn:aws:iam::123456789012:server-certificate/my-server-cert --ssl-policy ELBSecurityPolicy-2015-05 --default-actions Type=forward,TargetGroupArn=arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-targets/73e2d6bc24d8a067

Output::

  {
    "Listeners": [
        {
            "Protocol": "HTTPS",
            "DefaultActions": [
                {
                    "TargetGroupArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-targets/73e2d6bc24d8a067",
                    "Type": "forward"
                }
            ],
            "SslPolicy": "ELBSecurityPolicy-2015-05",
            "Certificates": [
                {
                    "CertificateArn": "arn:aws:iam::123456789012:server-certificate/my-server-cert"
                }
            ],
            "LoadBalancerArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188",
            "Port": 443,
            "ListenerArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:listener/app/my-load-balancer/50dc6c495c0c9188/f2f7dc8efc522ab2"
        }
    ]
  }


======
Output
======

Listeners -> (list)

  

  Information about the listener.

  

  (structure)

    

    Information about a listener.

    

    ListenerArn -> (string)

      

      The Amazon Resource Name (ARN) of the listener.

      

      

    LoadBalancerArn -> (string)

      

      The Amazon Resource Name (ARN) of the load balancer.

      

      

    Port -> (integer)

      

      The port on which the load balancer is listening.

      

      

    Protocol -> (string)

      

      The protocol for connections from clients to the load balancer.

      

      

    Certificates -> (list)

      

      The SSL server certificate. You must provide a certificate if the protocol is HTTPS.

      

      (structure)

        

        Information about an SSL server certificate deployed on a load balancer.

        

        CertificateArn -> (string)

          

          The Amazon Resource Name (ARN) of the certificate.

          

          

        

      

    SslPolicy -> (string)

      

      The security policy that defines which ciphers and protocols are supported. The default is the current predefined security policy.

      

      

    DefaultActions -> (list)

      

      The default actions for the listener.

      

      (structure)

        

        Information about an action.

        

        Type -> (string)

          

          The type of action.

          

          

        TargetGroupArn -> (string)

          

          The Amazon Resource Name (ARN) of the target group.

          

          

        

      

    

  

