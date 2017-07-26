[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam add-client-id-to-open-id-connect-provider:


*****************************************
add-client-id-to-open-id-connect-provider
*****************************************



===========
Description
===========



Adds a new client ID (also known as audience) to the list of client IDs already registered for the specified IAM OpenID Connect provider.

 

This action is idempotent; it does not fail or return an error if you add an existing client ID to the provider.



========
Synopsis
========

::

    add-client-id-to-open-id-connect-provider
  --open-id-connect-provider-arn <value>
  --client-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--open-id-connect-provider-arn`` (string)


  The Amazon Resource Name (ARN) of the IAM OpenID Connect (OIDC) provider to add the client ID to. You can get a list of OIDC provider ARNs by using the  list-open-id-connect-providers action. 

  

``--client-id`` (string)


  The client ID (also known as audience) to add to the IAM OpenID Connect provider.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To add a client ID (audience) to an Open-ID Connect (OIDC) provider**

The following ``add-client-id-to-open-id-connect-provider`` command adds the client ID ``my-application-ID`` to the OIDC provider named ``server.example.com``::

  aws iam add-client-id-to-open-id-connect-provider --client-id my-application-ID --open-id-connect-provider-arn arn:aws:iam::123456789012:oidc-provider/server.example.com

To create an OIDC provider, use the ``create-open-id-connect-provider`` command.

For more information, see `Using OpenID Connect Identity Providers`_ in the *Using IAM* guide.

.. _`Using OpenID Connect Identity Providers`: http://docs.aws.amazon.com/IAM/latest/UserGuide/identity-providers-oidc.html

======
Output
======

None