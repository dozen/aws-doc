[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb describe-load-balancer-policy-types:


***********************************
describe-load-balancer-policy-types
***********************************



===========
Description
===========



Describes the specified load balancer policy types.

 

You can use these policy types with  create-load-balancer-policy to create policy configurations for a load balancer.



========
Synopsis
========

::

    describe-load-balancer-policy-types
  [--policy-type-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-type-names`` (list)


  The names of the policy types. If no names are specified, describes all policy types defined by Elastic Load Balancing.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe the load balancer policy types defined by Elastic Load Balancing**

This example describes the load balancer policy types that you can use to create policy configurations for your load balancer.

Command::

     aws elb describe-load-balancer-policy-types

Output::

  {
    "PolicyTypeDescriptions": [
        {
            "PolicyAttributeTypeDescriptions": [
                {
                    "Cardinality": "ONE",
                    "AttributeName": "ProxyProtocol",
                    "AttributeType": "Boolean"
                }
            ],
            "PolicyTypeName": "ProxyProtocolPolicyType",
            "Description": "Policy that controls whether to include the IP address and port of the originating request for TCP messages. This policy operates on TCP/SSL listeners only"
        },
        {
            "PolicyAttributeTypeDescriptions": [
                {
                    "Cardinality": "ONE",
                    "AttributeName": "PublicKey",
                    "AttributeType": "String"
                }
            ],
            "PolicyTypeName": "PublicKeyPolicyType",
            "Description": "Policy containing a list of public keys to accept when authenticating the back-end server(s). This policy cannot be applied directly to back-end servers or listeners but must be part of a BackendServerAuthenticationPolicyType."
        },
        {
            "PolicyAttributeTypeDescriptions": [
                {
                    "Cardinality": "ONE",
                    "AttributeName": "CookieName",
                    "AttributeType": "String"
                }
            ],
            "PolicyTypeName": "AppCookieStickinessPolicyType",
            "Description": "Stickiness policy with session lifetimes controlled by the lifetime of the application-generated cookie. This policy can be associated only with HTTP/HTTPS listeners."
        },
        {
            "PolicyAttributeTypeDescriptions": [
                {
                    "Cardinality": "ZERO_OR_ONE",
                    "AttributeName": "CookieExpirationPeriod",
                    "AttributeType": "Long"
                } 
            ],
            "PolicyTypeName": "LBCookieStickinessPolicyType",
            "Description": "Stickiness policy with session lifetimes controlled by the browser (user-agent) or a specified expiration period. This policy can be associated only with HTTP/HTTPS listeners."
        },
        {
            "PolicyAttributeTypeDescriptions": [
                .
                .
                .
            ],
            "PolicyTypeName": "SSLNegotiationPolicyType",
            "Description": "Listener policy that defines the ciphers and protocols that will be accepted by the load balancer. This policy can be associated only with HTTPS/SSL listeners."
        },
        {
            "PolicyAttributeTypeDescriptions": [
                {
                    "Cardinality": "ONE_OR_MORE",
                    "AttributeName": "PublicKeyPolicyName",
                    "AttributeType": "PolicyName"
                }
            ],
            "PolicyTypeName": "BackendServerAuthenticationPolicyType",
            "Description": "Policy that controls authentication to back-end server(s) and contains one or more policies, such as an instance of a PublicKeyPolicyType. This policy can be associated only with back-end servers that are using HTTPS/SSL."
        }
    ]
  }


======
Output
======

PolicyTypeDescriptions -> (list)

  

  Information about the policy types.

  

  (structure)

    

    Information about a policy type.

    

    PolicyTypeName -> (string)

      

      The name of the policy type.

      

      

    Description -> (string)

      

      A description of the policy type.

      

      

    PolicyAttributeTypeDescriptions -> (list)

      

      The description of the policy attributes associated with the policies defined by Elastic Load Balancing.

      

      (structure)

        

        Information about a policy attribute type.

        

        AttributeName -> (string)

          

          The name of the attribute.

          

          

        AttributeType -> (string)

          

          The type of the attribute. For example, ``Boolean`` or ``Integer`` .

          

          

        Description -> (string)

          

          A description of the attribute.

          

          

        DefaultValue -> (string)

          

          The default value of the attribute, if applicable.

          

          

        Cardinality -> (string)

          

          The cardinality of the attribute.

           

          Valid values:

           

           
          * ONE(1) : Single value required
           
          * ZERO_OR_ONE(0..1) : Up to one value can be supplied
           
          * ZERO_OR_MORE(0..*) : Optional. Multiple values are allowed
           
          * ONE_OR_MORE(1..*0) : Required. Multiple values are allowed
           

          

          

        

      

    

  

