[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-open-id-connect-provider-thumbprint:


******************************************
update-open-id-connect-provider-thumbprint
******************************************



===========
Description
===========



Replaces the existing list of server certificate thumbprints associated with an OpenID Connect (OIDC) provider resource object with a new list of thumbprints.

 

The list that you pass with this action completely replaces the existing list of thumbprints. (The lists are not merged.)

 

Typically, you need to update a thumbprint only when the identity provider's certificate changes, which occurs rarely. However, if the provider's certificate *does* change, any attempt to assume an IAM role that specifies the OIDC provider as a principal fails until the certificate thumbprint is updated.

 

.. note::

   

  Because trust for the OIDC provider is ultimately derived from the provider's certificate and is validated by the thumbprint, it is a best practice to limit access to the ``update-open-id-connect-provider-thumbprint`` action to highly-privileged users.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/UpdateOpenIDConnectProviderThumbprint>`_


========
Synopsis
========

::

    update-open-id-connect-provider-thumbprint
  --open-id-connect-provider-arn <value>
  --thumbprint-list <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--open-id-connect-provider-arn`` (string)


  The Amazon Resource Name (ARN) of the IAM OIDC provider resource object for which you want to update the thumbprint. You can get a list of OIDC provider ARNs by using the  list-open-id-connect-providers action.

   

  For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ in the *AWS General Reference* .

  

``--thumbprint-list`` (list)


  A list of certificate thumbprints that are associated with the specified IAM OpenID Connect provider. For more information, see  create-open-id-connect-provider . 

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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