[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-open-id-connect-provider:


****************************
get-open-id-connect-provider
****************************



===========
Description
===========



Returns information about the specified OpenID Connect provider.



========
Synopsis
========

::

    get-open-id-connect-provider
  --open-id-connect-provider-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--open-id-connect-provider-arn`` (string)


  The Amazon Resource Name (ARN) of the IAM OpenID Connect (OIDC) provider to get information for. You can get a list of OIDC provider ARNs by using the  list-open-id-connect-providers action.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To return information about the specified OpenID Connect provider**

This example returns details about the OpenID Connect provider whose ARN is ``arn:aws:iam::123456789012:oidc-provider/server.example.com``::

  aws iam get-open-id-connect-provider --open-id-connect-provider-arn arn:aws:iam::123456789012:oidc-provider/server.example.com

Output::

  {
      "Url": "server.example.com"
          "CreateDate": "2015-06-16T19:41:48Z",
          "ThumbprintList": [
			"12345abcdefghijk67890lmnopqrst987example"
		  ],
          "ClientIDList": [
			"example-application-ID"
		  ]
  }

For more information, see `Using OpenID Connect Identity Providers`_ in the *Using IAM* guide.

.. _`Using OpenID Connect Identity Providers`: http://docs.aws.amazon.com/IAM/latest/UserGuide/identity-providers-oidc.html

======
Output
======

Url -> (string)

  

  The URL that the IAM OpenID Connect provider is associated with. For more information, see  create-open-id-connect-provider . 

  

  

ClientIDList -> (list)

  

  A list of client IDs (also known as audiences) that are associated with the specified IAM OpenID Connect provider. For more information, see  create-open-id-connect-provider . 

  

  (string)

    

    

  

ThumbprintList -> (list)

  

  A list of certificate thumbprints that are associated with the specified IAM OpenID Connect provider. For more information, see  create-open-id-connect-provider . 

  

  (string)

    

    Contains a thumbprint for an identity provider's server certificate.

     

    The identity provider's server certificate thumbprint is the hex-encoded SHA-1 hash value of the self-signed X.509 certificate used by the domain where the OpenID Connect provider makes its keys available. It is always a 40-character string. 

    

    

  

CreateDate -> (timestamp)

  

  The date and time when the IAM OpenID Connect provider entity was created in the AWS account. 

  

  

