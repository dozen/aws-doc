[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses set-identity-mail-from-domain:


*****************************
set-identity-mail-from-domain
*****************************



===========
Description
===========



Enables or disables the custom MAIL FROM domain setup for a verified identity (an email address or a domain).

 

.. warning::

   

  To send emails using the specified MAIL FROM domain, you must add an MX record to your MAIL FROM domain's DNS settings. If you want your emails to pass Sender Policy Framework (SPF) checks, you must also add or update an SPF record. For more information, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/mail-from-set.html>`_ .

   

 

This action is throttled at one request per second.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/SetIdentityMailFromDomain>`_


========
Synopsis
========

::

    set-identity-mail-from-domain
  --identity <value>
  [--mail-from-domain <value>]
  [--behavior-on-mx-failure <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity`` (string)


  The verified identity for which you want to enable or disable the specified custom MAIL FROM domain.

  

``--mail-from-domain`` (string)


  The custom MAIL FROM domain that you want the verified identity to use. The MAIL FROM domain must 1) be a subdomain of the verified identity, 2) not be used in a "From" address if the MAIL FROM domain is the destination of email feedback forwarding (for more information, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/mail-from.html>`_ ), and 3) not be used to receive emails. A value of ``null`` disables the custom MAIL FROM setting for the identity.

  

``--behavior-on-mx-failure`` (string)


  The action that you want Amazon SES to take if it cannot successfully read the required MX record when you send an email. If you choose ``UseDefaultValue`` , Amazon SES will use amazonses.com (or a subdomain of that) as the MAIL FROM domain. If you choose ``RejectMessage`` , Amazon SES will return a ``MailFromDomainNotVerified`` error and not send the email.

   

  The action specified in ``behavior-on-mx-failure`` is taken when the custom MAIL FROM domain setup is in the ``Pending`` , ``Failed`` , and ``TemporaryFailure`` states.

  

  Possible values:

  
  *   ``UseDefaultValue``

  
  *   ``RejectMessage``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

