[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-open-id-connect-provider-thumbprint:


******************************************
update-open-id-connect-provider-thumbprint
******************************************



===========
Description
===========



Replaces the existing list of server certificate thumbprints with a new list. 

 

The list that you pass with this action completely replaces the existing list of thumbprints. (The lists are not merged.)

 

Typically, you need to update a thumbprint only when the identity provider's certificate changes, which occurs rarely. However, if the provider's certificate *does* change, any attempt to assume an IAM role that specifies the OIDC provider as a principal will fail until the certificate thumbprint is updated.

 

.. note::

  Because trust for the OpenID Connect provider is ultimately derived from the provider's certificate and is validated by the thumbprint, it is a best practice to limit access to the ``update-open-id-connect-provider-thumbprint`` action to highly-privileged users. 



========
Synopsis
========

::

    update-open-id-connect-provider-thumbprint
  --open-id-connect-provider-arn <value>
  --thumbprint-list <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--open-id-connect-provider-arn`` (string)


  The Amazon Resource Name (ARN) of the IAM OpenID Connect (OIDC) provider to update the thumbprint for. You can get a list of OIDC provider ARNs by using the  list-open-id-connect-providers action. 

  

``--thumbprint-list`` (list)


  A list of certificate thumbprints that are associated with the specified IAM OpenID Connect provider. For more information, see  create-open-id-connect-provider . 

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To replace the existing list of server certificate thumbprints with a new list**

This example updates the certificate thumbprint list for the OIDC provider whose ARN is 
``arn:aws:iam::123456789012:oidc-provider/example.oidcprovider.com`` to use a new thumbprint::

  aws iam update-open-id-connect-provider-thumbprint --open-id-connect-provider-arn arn:aws:iam::123456789012:oidc-provider/example.oidcprovider.com --thumbprint-list 7359755EXAMPLEabc3060bce3EXAMPLEec4542a3


For more information, see `Using OpenID Connect Identity Providers`_ in the *Using IAM* guide.

.. _`Using OpenID Connect Identity Providers`: http://docs.aws.amazon.com/IAM/latest/UserGuide/identity-providers-oidc.html

======
Output
======

None