[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam create-open-id-connect-provider:


*******************************
create-open-id-connect-provider
*******************************



===========
Description
===========



Creates an IAM entity to describe an identity provider (IdP) that supports `OpenID Connect (OIDC) <http://openid.net/connect/>`_ .

 

The OIDC provider that you create with this operation can be used as a principal in a role's trust policy to establish a trust relationship between AWS and the OIDC provider.

 

When you create the IAM OIDC provider, you specify the URL of the OIDC identity provider (IdP) to trust, a list of client IDs (also known as audiences) that identify the application or applications that are allowed to authenticate using the OIDC provider, and a list of thumbprints of the server certificate(s) that the IdP uses. You get all of this information from the OIDC IdP that you want to use for access to AWS.

 

.. note::

   

  Because trust for the OIDC provider is ultimately derived from the IAM provider that this action creates, it is a best practice to limit access to the  create-open-id-connect-provider action to highly-privileged users.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/CreateOpenIDConnectProvider>`_


========
Synopsis
========

::

    create-open-id-connect-provider
  --url <value>
  [--client-id-list <value>]
  --thumbprint-list <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--url`` (string)


  The URL of the identity provider. The URL must begin with "https://" and should correspond to the ``iss`` claim in the provider's OpenID Connect ID tokens. Per the OIDC standard, path components are allowed but query parameters are not. Typically the URL consists of only a host name, like "https://server.example.org" or "https://example.com".

   

  You cannot register the same provider multiple times in a single AWS account. If you try to submit a URL that has already been used for an OpenID Connect provider in the AWS account, you will get an error.

  

``--client-id-list`` (list)


  A list of client IDs (also known as audiences). When a mobile or web app registers with an OpenID Connect provider, they establish a value that identifies the application. (This is the value that's sent as the ``client_id`` parameter on OAuth requests.)

   

  You can register multiple client IDs with the same provider. For example, you might have multiple applications that use the same OIDC provider. You cannot register more than 100 client IDs with a single IAM OIDC provider.

   

  There is no defined format for a client ID. The ``CreateOpenIDConnectProviderRequest`` action accepts client IDs up to 255 characters long.

  



Syntax::

  "string" "string" ...



``--thumbprint-list`` (list)


  A list of server certificate thumbprints for the OpenID Connect (OIDC) identity provider's server certificate(s). Typically this list includes only one entry. However, IAM lets you have up to five thumbprints for an OIDC provider. This lets you maintain multiple thumbprints if the identity provider is rotating certificates.

   

  The server certificate thumbprint is the hex-encoded SHA-1 hash value of the X.509 certificate used by the domain where the OpenID Connect provider makes its keys available. It is always a 40-character string.

   

  You must provide at least one thumbprint when creating an IAM OIDC provider. For example, if the OIDC provider is ``server.example.com`` and the provider stores its keys at "https://keys.server.example.com/openid-connect", the thumbprint string would be the hex-encoded SHA-1 hash value of the certificate used by https://keys.server.example.com.

   

  For more information about obtaining the OIDC provider's thumbprint, see `Obtaining the Thumbprint for an OpenID Connect Provider <http://docs.aws.amazon.com/IAM/latest/UserGuide/identity-providers-oidc-obtain-thumbprint.html>`_ in the *IAM User Guide* .

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create an OpenID Connect (OIDC) provider**

To create an OpenID Connect (OIDC) provider, we recommend using the ``--cli-input-json`` parameter to pass a JSON file that contains the required parameters. When you create an OIDC provider, you must pass the URL of the provider, and the URL must begin with ``https://``. It can be difficult to pass the URL as a command line parameter, because the colon (:) and forward slash (/) characters have special meaning in some command line environments. Using the ``--cli-input-json`` parameter gets around this limitation.

To use the ``--cli-input-json`` parameter, start by using the ``create-open-id-connect-provider`` command with the ``--generate-cli-skeleton`` parameter, as in the following example::

  aws iam create-open-id-connect-provider --generate-cli-skeleton > create-open-id-connect-provider.json

The previous command creates a JSON file called create-open-id-connect-provider.json that you can use to fill in the information for a subsequent ``create-open-id-connect-provider`` command. For example::

  {
      "Url": "https://server.example.com",
      "ClientIDList": [
          "example-application-ID"
      ],
      "ThumbprintList": [
          "c3768084dfb3d2b68b7897bf5f565da8eEXAMPLE"
      ]
  }

Next, to create the OpenID Connect (OIDC) provider, use the ``create-open-id-connect-provider`` command again, this time passing the ``--cli-input-json`` parameter to specify your JSON file. The following ``create-open-id-connect-provider`` command uses the ``--cli-input-json`` parameter with a JSON file called create-open-id-connect-provider.json::

  aws iam create-open-id-connect-provider --cli-input-json file://create-open-id-connect-provider.json

Output::

  {
      "OpenIDConnectProviderArn": "arn:aws:iam::123456789012:oidc-provider/server.example.com"
  }

For more information about OIDC providers, see `Using OpenID Connect Identity Providers`_ in the *Using IAM* guide. 

For more information about obtaining thumbprints for an OIDC provider, see `Obtaining the Thumbprint for an OpenID Connect Provider`_ in the *Using IAM* guide.

.. _`Using OpenID Connect Identity Providers`: http://docs.aws.amazon.com/IAM/latest/UserGuide/identity-providers-oidc.html

.. _`Obtaining the Thumbprint for an OpenID Connect Provider`: http://docs.aws.amazon.com/IAM/latest/UserGuide/identity-providers-oidc-obtain-thumbprint.html

======
Output
======

OpenIDConnectProviderArn -> (string)

  

  The Amazon Resource Name (ARN) of the new IAM OpenID Connect provider that is created. For more information, see  OpenIDConnectProviderListEntry . 

  

  

