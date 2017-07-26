[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-saml-providers:


*******************
list-saml-providers
*******************



===========
Description
===========



Lists the SAML provider resource objects defined in IAM in the account.

 

.. note::

   

  This operation requires `Signature Version 4 <http://docs.aws.amazon.com/general/latest/gr/signature-version-4.html>`_ .

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/ListSAMLProviders>`_


========
Synopsis
========

::

    list-saml-providers
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list the SAML providers in the AWS account**

This example retrieves the list of SAML 2.0 providers created in the current AWS account::

  aws iam list-saml-providers

Output::

  {
    "SAMLProviderList": [
      {
        "CreateDate": "2015-06-05T22:45:14Z",
        "ValidUntil": "2015-06-05T22:45:14Z",
        "Arn": "arn:aws:iam::123456789012:saml-provider/SAMLADFS"
      }
    ]
  }

For more information, see `Using SAML Providers`_ in the *Using IAM* guide.

.. _`Using SAML Providers`: http://docs.aws.amazon.com/IAM/latest/UserGuide/identity-providers-saml.html

======
Output
======

SAMLProviderList -> (list)

  

  The list of SAML provider resource objects defined in IAM for this AWS account.

  

  (structure)

    

    Contains the list of SAML providers for this account.

    

    Arn -> (string)

      

      The Amazon Resource Name (ARN) of the SAML provider.

      

      

    ValidUntil -> (timestamp)

      

      The expiration date and time for the SAML provider.

      

      

    CreateDate -> (timestamp)

      

      The date and time when the SAML provider was created.

      

      

    

  

