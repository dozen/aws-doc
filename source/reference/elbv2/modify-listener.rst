[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 modify-listener:


***************
modify-listener
***************



===========
Description
===========



Modifies the specified properties of the specified listener.

 

Any properties that you do not specify retain their current values. However, changing the protocol from HTTPS to HTTP removes the security policy and SSL certificate properties. If you change the protocol from HTTP to HTTPS, you must add the security policy and server certificate.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/ModifyListener>`_


========
Synopsis
========

::

    modify-listener
  --listener-arn <value>
  [--port <value>]
  [--protocol <value>]
  [--ssl-policy <value>]
  [--certificates <value>]
  [--default-actions <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--listener-arn`` (string)


  The Amazon Resource Name (ARN) of the listener.

  

``--port`` (integer)


  The port for connections from clients to the load balancer.

  

``--protocol`` (string)


  The protocol for connections from clients to the load balancer.

  

  Possible values:

  
  *   ``HTTP``

  
  *   ``HTTPS``

  

  

``--ssl-policy`` (string)


  The security policy that defines which protocols and ciphers are supported. For more information, see `Security Policies <http://docs.aws.amazon.com/elasticloadbalancing/latest/application/create-https-listener.html#describe-ssl-policies>`_ in the *Application Load Balancers Guide* .

  

``--certificates`` (list)


  The SSL server certificate.

  



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


  The default actions.

  



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

**To change the default action**

This example changes the default action for the specified listener.

Command::

  aws elbv2 modify-listener --listener-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:listener/app/my-load-balancer/50dc6c495c0c9188/f2f7dc8efc522ab2 --default-actions Type=forward,TargetGroupArn=arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-new-targets/2453ed029918f21f

Output::

  {
    "Listeners": [
        {
            "Protocol": "HTTP",
            "DefaultActions": [
                {
                    "TargetGroupArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:targetgroup/my-new-targets/2453ed029918f21f",
                    "Type": "forward"
                }
            ],
            "LoadBalancerArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188",
            "Port": 80,
            "ListenerArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:listener/app/my-load-balancer/50dc6c495c0c9188/f2f7dc8efc522ab2"
        }
    ]
  }

**To change the server certificate**

This example changes the server certificate for the specified HTTPS listener.

Command::

  aws elbv2 modify-listener --listener-arn arn:aws:elasticloadbalancing:us-west-2:123456789012:listener/app/my-load-balancer/50dc6c495c0c9188/0467ef3c8400ae65 --certificates CertificateArn=arn:aws:iam::123456789012:server-certificate/my-new-server-cert

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
                    "CertificateArn": "arn:aws:iam::123456789012:server-certificate/my-new-server-cert"
                }
            ],
            "LoadBalancerArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:loadbalancer/app/my-load-balancer/50dc6c495c0c9188",
            "Port": 443,
            "ListenerArn": "arn:aws:elasticloadbalancing:us-west-2:123456789012:listener/app/my-load-balancer/50dc6c495c0c9188/0467ef3c8400ae65"
        }
    ]
  }


======
Output
======

Listeners -> (list)

  

  Information about the modified listeners.

  

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

          

          

        

      

    

  

