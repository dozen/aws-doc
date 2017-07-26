[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb describe-load-balancer-policies:


*******************************
describe-load-balancer-policies
*******************************



===========
Description
===========



Describes the specified policies.

 

If you specify a load balancer name, the action returns the descriptions of all policies created for the load balancer. If you specify a policy name associated with your load balancer, the action returns the description of that policy. If you don't specify a load balancer name, the action returns descriptions of the specified sample policies, or descriptions of all sample policies. The names of the sample policies have the ``ELBSample-`` prefix.



========
Synopsis
========

::

    describe-load-balancer-policies
  [--load-balancer-name <value>]
  [--policy-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--policy-names`` (list)


  The names of the policies.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe all policies associated with a load balancer**

This example describes all of the policies associated with the specified load balancer.

Command::

  aws elb describe-load-balancer-policies --load-balancer-name my-load-balancer

Output::

  {
    "PolicyDescriptions": [
      {
        "PolicyAttributeDescriptions": [
          {
            "AttributeName": "ProxyProtocol",
            "AttributeValue": "true"
          }
        ],
        "PolicyName": "my-ProxyProtocol-policy",
        "PolicyTypeName": "ProxyProtocolPolicyType"
      },
      {
          "PolicyAttributeDescriptions": [
              {
                  "AttributeName": "CookieName",
                  "AttributeValue": "my-app-cookie"
              }
          ],
          "PolicyName": "my-app-cookie-policy",
          "PolicyTypeName": "AppCookieStickinessPolicyType"
      },
      {
        "PolicyAttributeDescriptions": [
          {
            "AttributeName": "CookieExpirationPeriod",
            "AttributeValue": "60"
          }
        ],
        "PolicyName": "my-duration-cookie-policy",
        "PolicyTypeName": "LBCookieStickinessPolicyType"
      },
      .
      .
      .
    ]
  }

**To describe a specific policy associated with a load balancer**

This example describes the specified policy associated with the specified load balancer.

Command::

  aws elb describe-load-balancer-policies --load-balancer-name my-load-balancer --policy-name my-authentication-policy

Output::

  {
    "PolicyDescriptions": [
        {
            "PolicyAttributeDescriptions": [
                {
                    "AttributeName": "PublicKeyPolicyName",
                    "AttributeValue": "my-PublicKey-policy"
                }
            ],
            "PolicyName": "my-authentication-policy",
            "PolicyTypeName": "BackendServerAuthenticationPolicyType"
        }
    ]
  }


======
Output
======

PolicyDescriptions -> (list)

  

  Information about the policies.

  

  (structure)

    

    Information about a policy.

    

    PolicyName -> (string)

      

      The name of the policy.

      

      

    PolicyTypeName -> (string)

      

      The name of the policy type.

      

      

    PolicyAttributeDescriptions -> (list)

      

      The policy attributes.

      

      (structure)

        

        Information about a policy attribute.

        

        AttributeName -> (string)

          

          The name of the attribute.

          

          

        AttributeValue -> (string)

          

          The value of the attribute.

          

          

        

      

    

  

