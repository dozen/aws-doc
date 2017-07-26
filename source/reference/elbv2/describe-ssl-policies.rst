[ :ref:`aws <cli:aws>` . :ref:`elbv2 <cli:aws elbv2>` ]

.. _cli:aws elbv2 describe-ssl-policies:


*********************
describe-ssl-policies
*********************



===========
Description
===========



Describes the specified policies or all policies used for SSL negotiation.

 

For more information, see `Security Policies <http://docs.aws.amazon.com/elasticloadbalancing/latest/application/create-https-listener.html#describe-ssl-policies>`_ in the *Application Load Balancers Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancingv2-2015-12-01/DescribeSSLPolicies>`_


========
Synopsis
========

::

    describe-ssl-policies
  [--names <value>]
  [--marker <value>]
  [--page-size <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--names`` (list)


  The names of the policies.

  



Syntax::

  "string" "string" ...



``--marker`` (string)


  The marker for the next set of results. (You received this marker from a previous call.)

  

``--page-size`` (integer)


  The maximum number of results to return with this call.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a policy used for SSL negotiation**

This example describes the specified policy used for SSL negotiation.

Command::

  aws elbv2 describe-ssl-policies --names ELBSecurityPolicy-2015-05
      
Output::

  {
    "SslPolicies": [
        {
            "SslProtocols": [
                "TLSv1",
                "TLSv1.1",
                "TLSv1.2"
            ],
            "Ciphers": [
                {
                    "Priority": 1,
                    "Name": "ECDHE-ECDSA-AES128-GCM-SHA256"
                },
                {
                    "Priority": 2,
                    "Name": "ECDHE-RSA-AES128-GCM-SHA256"
                },
                {
                    "Priority": 3,
                    "Name": "ECDHE-ECDSA-AES128-SHA256"
                },

                ...

                {
                    "Priority": 19,
                    "Name": "AES256-SHA"
                }
            ],
            "Name": "ELBSecurityPolicy-2015-05"
        }
    ]
  }

**To describe all policies used for SSL negotiation**

This example describes all the policies that you can use for SSL negotiation.

Command::

  aws elbv2 describe-ssl-policies


======
Output
======

SslPolicies -> (list)

  

  Information about the policies.

  

  (structure)

    

    Information about a policy used for SSL negotiation.

    

    SslProtocols -> (list)

      

      The protocols.

      

      (string)

        

        

      

    Ciphers -> (list)

      

      The ciphers.

      

      (structure)

        

        Information about a cipher used in a policy.

        

        Name -> (string)

          

          The name of the cipher.

          

          

        Priority -> (integer)

          

          The priority of the cipher.

          

          

        

      

    Name -> (string)

      

      The name of the policy.

      

      

    

  

NextMarker -> (string)

  

  The marker to use when requesting the next set of results. If there are no additional results, the string is empty.

  

  

