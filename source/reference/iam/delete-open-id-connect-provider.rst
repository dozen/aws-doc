[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-open-id-connect-provider:


*******************************
delete-open-id-connect-provider
*******************************



===========
Description
===========



Deletes an IAM OpenID Connect identity provider.

 

Deleting an OIDC provider does not update any roles that reference the provider as a principal in their trust policies. Any attempt to assume a role that references a provider that has been deleted will fail. 

 

This action is idempotent; it does not fail or return an error if you call the action for a provider that was already deleted.



========
Synopsis
========

::

    delete-open-id-connect-provider
  --open-id-connect-provider-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--open-id-connect-provider-arn`` (string)


  The Amazon Resource Name (ARN) of the IAM OpenID Connect provider to delete. You can get a list of OpenID Connect provider ARNs by using the  list-open-id-connect-providers action.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete an IAM OpenID Connect identity provider**

This example deletes the IAM OIDC provider that connects to the provider ``example.oidcprovider.com``::

  aws aim delete-open-id-connect-provider --open-id-connect-provider-arn arn:aws:iam::123456789012:oidc-provider/example.oidcprovider.com


For more information, see `Using OpenID Connect Identity Providers`_ in the *Using IAM* guide.

.. _`Using OpenID Connect Identity Providers`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_CreatingAndListingGroups.html

======
Output
======

None