[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-saml-provider:


*****************
get-saml-provider
*****************



===========
Description
===========



Returns the SAML provider metadocument that was uploaded when the provider was created or updated. 

 

.. note::

  This operation requires `Signature Version 4`_ . 



========
Synopsis
========

::

    get-saml-provider
  --saml-provider-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--saml-provider-arn`` (string)


  The Amazon Resource Name (ARN) of the SAML provider to get information about.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To retrieve the SAML provider metadocument**

This example retrieves the details about the SAML 2.0 provider whose ARM is ``arn:aws:iam::123456789012:saml-provider/SAMLADFS``. 
The response includes the metadata document that you got from the identity provider to create the AWS SAML provider entity as well 
as the creation and expiration dates::

  aws iam get-saml-provider --saml-provider-arn arn:aws:iam::123456789012:saml-provider/SAMLADFS 


For more information, see `Using SAML Providers`_ in the *Using IAM* guide.

.. _`Using SAML Providers`: http://docs.aws.amazon.com/IAM/latest/UserGuide/identity-providers-saml.html

======
Output
======

SAMLMetadataDocument -> (string)

  

  The XML metadata document that includes information about an identity provider.

  

  

CreateDate -> (timestamp)

  

  The date and time when the SAML provider was created.

  

  

ValidUntil -> (timestamp)

  

  The expiration date and time for the SAML provider.

  

  



.. _Signature Version 4: http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html
