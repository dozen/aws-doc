[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-saml-provider:


********************
delete-saml-provider
********************



===========
Description
===========



Deletes a SAML provider resource in IAM.

 

Deleting the provider resource from IAM does not update any roles that reference the SAML provider resource's ARN as a principal in their trust policies. Any attempt to assume a role that references a non-existent provider resource ARN fails.

 

.. note::

   

  This operation requires `Signature Version 4 <http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html>`_ .

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/DeleteSAMLProvider>`_


========
Synopsis
========

::

    delete-saml-provider
  --saml-provider-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--saml-provider-arn`` (string)


  The Amazon Resource Name (ARN) of the SAML provider to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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