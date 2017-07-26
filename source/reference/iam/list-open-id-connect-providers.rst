[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-open-id-connect-providers:


******************************
list-open-id-connect-providers
******************************



===========
Description
===========



Lists information about the IAM OpenID Connect (OIDC) provider resource objects defined in the AWS account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/ListOpenIDConnectProviders>`_


========
Synopsis
========

::

    list-open-id-connect-providers
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list information about the OpenID Connect providers in the AWS account**

This example returns a list of ARNS of all the OpenID Connect providers that are defined in the current AWS account::

  aws iam list-open-id-connect-providers 

Output::

  {
    "OpenIDConnectProviderList": [
      {
        "Arn": "arn:aws:iam::123456789012:oidc-provider/example.oidcprovider.com"
      }
    ]
  }

For more information, see `Using OpenID Connect Identity Providers`_ in the *Using IAM* guide.

.. _`Using OpenID Connect Identity Providers`: http://docs.aws.amazon.com/IAM/latest/UserGuide/identity-providers-oidc.html

======
Output
======

OpenIDConnectProviderList -> (list)

  

  The list of IAM OIDC provider resource objects defined in the AWS account.

  

  (structure)

    

    Contains the Amazon Resource Name (ARN) for an IAM OpenID Connect provider.

    

    Arn -> (string)

      

      The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources.

       

      For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ in the *AWS General Reference* . 

      

      

    

  

