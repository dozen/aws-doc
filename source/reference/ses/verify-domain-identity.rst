[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses verify-domain-identity:


**********************
verify-domain-identity
**********************



===========
Description
===========



Verifies a domain.

 

This action is throttled at one request per second.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/VerifyDomainIdentity>`_


========
Synopsis
========

::

    verify-domain-identity
  --domain <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain`` (string)


  The domain to be verified.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To verify a domain with Amazon SES**

The following example uses the ``verify-domain-identity`` command to verify a domain::

    aws ses verify-domain-identity --domain example.com

Output::

 {
    "VerificationToken": "eoEmxw+YaYhb3h3iVJHuXMJXqeu1q1/wwmvjuEXAMPLE"
 }


To complete domain verification, you must add a TXT record with the returned verification token to your domain's DNS settings. For more information, see `Verifying Domains in Amazon SES`_ in the *Amazon Simple Email Service Developer Guide*.

.. _`Verifying Domains in Amazon SES`: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/verify-domains.html


======
Output
======

VerificationToken -> (string)

  

  A TXT record that must be placed in the DNS settings for the domain, in order to complete domain verification.

  

  

