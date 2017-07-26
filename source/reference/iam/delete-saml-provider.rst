[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-saml-provider:


********************
delete-saml-provider
********************



===========
Description
===========



Deletes a SAML provider.

 

Deleting the provider does not update any roles that reference the SAML provider as a principal in their trust policies. Any attempt to assume a role that references a SAML provider that has been deleted will fail. 

 

.. note::

  This operation requires `Signature Version 4`_ . 



========
Synopsis
========

::

    delete-saml-provider
  --saml-provider-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--saml-provider-arn`` (string)


  The Amazon Resource Name (ARN) of the SAML provider to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a SAML provider**

This example deletes the IAM SAML 2.0 provider whose ARN is ``arn:aws:iam::123456789012:saml-provider/SAMLADFSProvider``::

  aws iam delete-saml-provider --saml-provider-arn arn:aws:iam::123456789012:saml-provider/SAMLADFSProvider


For more information, see `Using SAML Providers`_ in the *Using IAM* guide.

.. _`Using SAML Providers`: http://docs.aws.amazon.com/IAM/latest/UserGuide/identity-providers-saml.html

======
Output
======

None

.. _Signature Version 4: http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html
