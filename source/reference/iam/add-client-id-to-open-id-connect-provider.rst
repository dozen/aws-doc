[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam add-client-id-to-open-id-connect-provider:


*****************************************
add-client-id-to-open-id-connect-provider
*****************************************



===========
Description
===========



Adds a new client ID (also known as audience) to the list of client IDs already registered for the specified IAM OpenID Connect (OIDC) provider resource.

 

This action is idempotent; it does not fail or return an error if you add an existing client ID to the provider.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/AddClientIDToOpenIDConnectProvider>`_


========
Synopsis
========

::

    add-client-id-to-open-id-connect-provider
  --open-id-connect-provider-arn <value>
  --client-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--open-id-connect-provider-arn`` (string)


  The Amazon Resource Name (ARN) of the IAM OpenID Connect (OIDC) provider resource to add the client ID to. You can get a list of OIDC provider ARNs by using the  list-open-id-connect-providers action.

  

``--client-id`` (string)


  The client ID (also known as audience) to add to the IAM OpenID Connect provider resource.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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