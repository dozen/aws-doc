[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb create-load-balancer-policy:


***************************
create-load-balancer-policy
***************************



===========
Description
===========



Creates a policy with the specified attributes for the specified load balancer.

 

Policies are settings that are saved for your load balancer and that can be applied to the listener or the application server, depending on the policy type.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/CreateLoadBalancerPolicy>`_


========
Synopsis
========

::

    create-load-balancer-policy
  --load-balancer-name <value>
  --policy-name <value>
  --policy-type-name <value>
  [--policy-attributes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--policy-name`` (string)


  The name of the load balancer policy to be created. This name must be unique within the set of policies for this load balancer.

  

``--policy-type-name`` (string)


  The name of the base policy type. To get the list of policy types, use  describe-load-balancer-policy-types .

  

``--policy-attributes`` (list)


  The policy attributes.

  



Shorthand Syntax::

    AttributeName=string,AttributeValue=string ...




JSON Syntax::

  [
    {
      "AttributeName": "string",
      "AttributeValue": "string"
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

**To create a policy that enables Proxy Protocol on a load balancer**

This example creates a policy that enables Proxy Protocol on the specified load balancer.

Command::

  aws elb create-load-balancer-policy --load-balancer-name my-load-balancer --policy-name my-ProxyProtocol-policy --policy-type-name ProxyProtocolPolicyType --policy-attributes AttributeName=ProxyProtocol,AttributeValue=true


**To create an SSL negotiation policy using the recommended security policy**

This example creates an SSL negotiation policy for the specified HTTPS load balancer using the recommended security policy.

Command::

  aws elb create-load-balancer-policy --load-balancer-name my-load-balancer --policy-name my-SSLNegotiation-policy --policy-type-name SSLNegotiationPolicyType --policy-attributes AttributeName=Reference-Security-Policy,AttributeValue=ELBSecurityPolicy-2015-03


**To create an SSL negotiation policy using a custom security policy**

This example creates an SSL negotiation policy for your HTTPS load balancer using a custom security policy by enabling the protocols and the ciphers.

Command::

  aws elb create-load-balancer-policy --load-balancer-name my-load-balancer --policy-name my-SSLNegotiation-policy --policy-type-name SSLNegotiationPolicyType --policy-attributes AttributeName=Protocol-SSLv3,AttributeValue=true AttributeName=Protocol-TLSv1.1,AttributeValue=true AttributeName=DHE-RSA-AES256-SHA256,AttributeValue=true AttributeName=Server-Defined-Cipher-Order,AttributeValue=true


**To create a public key policy**

This example creates a public key policy.

Command::

  aws elb create-load-balancer-policy --load-balancer-name my-load-balancer --policy-name my-PublicKey-policy --policy-type-name PublicKeyPolicyType --policy-attributes AttributeName=PublicKey,AttributeValue=MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAwAYUjnfyEyXr1pxjhFWBpMlggUcqoi3kl+dS74kj//c6x7ROtusUaeQCTgIUkayttRDWchuqo1pHC1u+n5xxXnBBe2ejbb2WRsKIQ5rXEeixsjFpFsojpSQKkzhVGI6mJVZBJDVKSHmswnwLBdofLhzvllpovBPTHe+o4haAWvDBALJU0pkSI1FecPHcs2hwxf14zHoXy1e2k36A64nXW43wtfx5qcVSIxtCEOjnYRg7RPvybaGfQ+v6Iaxb/+7J5kEvZhTFQId+bSiJImF1FSUT1W1xwzBZPUbcUkkXDj45vC2s3Z8E+Lk7a3uZhvsQHLZnrfuWjBWGWvZ/MhZYgEXAMPLE


**To create a backend server authentication policy**

This example creates a backend server authentication policy that enables authentication on your backend instance using a public key policy.

Command::

  aws elb create-load-balancer-policy --load-balancer-name my-load-balancer --policy-name my-authentication-policy --policy-type-name BackendServerAuthenticationPolicyType --policy-attributes AttributeName=PublicKeyPolicyName,AttributeValue=my-PublicKey-policy



======
Output
======

