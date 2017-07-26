[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam remove-client-id-from-open-id-connect-provider:


**********************************************
remove-client-id-from-open-id-connect-provider
**********************************************



===========
Description
===========



Removes the specified client ID (also known as audience) from the list of client IDs registered for the specified IAM OpenID Connect (OIDC) provider resource object.

 

This action is idempotent; it does not fail or return an error if you try to remove a client ID that does not exist.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/RemoveClientIDFromOpenIDConnectProvider>`_


========
Synopsis
========

::

    remove-client-id-from-open-id-connect-provider
  --open-id-connect-provider-arn <value>
  --client-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--open-id-connect-provider-arn`` (string)


  The Amazon Resource Name (ARN) of the IAM OIDC provider resource to remove the client ID from. You can get a list of OIDC provider ARNs by using the  list-open-id-connect-providers action.

   

  For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ in the *AWS General Reference* .

  

``--client-id`` (string)


  The client ID (also known as audience) to remove from the IAM OIDC provider resource. For more information about client IDs, see  create-open-id-connect-provider .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To remove the specified client ID from the list of client IDs registered for the specified IAM OpenID Connect provider**

This example removes the client ID ``My-TestApp-3`` from the list of client IDs associated with the IAM OIDC provider whose 
ARN is ``arn:aws:iam::123456789012:oidc-provider/example.oidcprovider.com``::

  aws iam remove-client-id-from-open-id-connect-provider --client-id My-TestApp-3 --open-id-connect-provider-arn arn:aws:iam::123456789012:oidc-provider/example.oidcprovider.com


For more information, see `Using OpenID Connect Identity Providers`_ in the *Using IAM* guide.

.. _`Using OpenID Connect Identity Providers`: http://docs.aws.amazon.com/IAM/latest/UserGuide/identity-providers-oidc.html

======
Output
======

None