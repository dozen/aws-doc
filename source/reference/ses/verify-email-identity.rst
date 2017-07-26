[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses verify-email-identity:


*********************
verify-email-identity
*********************



===========
Description
===========



Verifies an email address. This action causes a confirmation email message to be sent to the specified address.

 

This action is throttled at one request per second.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/VerifyEmailIdentity>`_


========
Synopsis
========

::

    verify-email-identity
  --email-address <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--email-address`` (string)


  The email address to be verified.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To verify an email address with Amazon SES**

The following example uses the ``verify-email-identity`` command to verify an email address::

    aws ses verify-email-identity --email-address user@example.com

Before you can send an email using Amazon SES, you must verify the address or domain that you are sending the email
from to prove that you own it. If you do not have production access yet, you also need to verify any email addresses
that you send emails to except for email addresses provided by the Amazon SES mailbox simulator.

After verify-email-identity is called, the email address will receive a verification email. The user must click on the link in
the email to complete the verification process.

For more information, see `Verifying Email Addresses in Amazon SES`_ in the *Amazon Simple Email Service Developer Guide*.

.. _`Verifying Email Addresses in Amazon SES`: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/verify-email-addresses.html


======
Output
======

