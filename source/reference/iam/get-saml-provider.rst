[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-saml-provider:


*****************
get-saml-provider
*****************



===========
Description
===========



Returns the SAML provider metadocument that was uploaded when the IAM SAML provider resource object was created or updated.

 

.. note::

   

  This operation requires `Signature Version 4 <http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html>`_ .

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/GetSAMLProvider>`_


========
Synopsis
========

::

    get-saml-provider
  --saml-provider-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--saml-provider-arn`` (string)


  The Amazon Resource Name (ARN) of the SAML provider resource object in IAM to get information about.

   

  For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ in the *AWS General Reference* .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  

