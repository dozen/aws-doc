[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains resend-contact-reachability-email:


*********************************
resend-contact-reachability-email
*********************************



===========
Description
===========



For operations that require confirmation that the email address for the registrant contact is valid, such as registering a new domain, this operation resends the confirmation email to the current email address for the registrant contact.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53domains-2014-05-15/ResendContactReachabilityEmail>`_


========
Synopsis
========

::

    resend-contact-reachability-email
  [--domain-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The name of the domain for which you want Amazon Route 53 to resend a confirmation email to the registrant contact.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

domainName -> (string)

  

  The domain name for which you requested a confirmation email.

  

  

emailAddress -> (string)

  

  The email address for the registrant contact at the time that we sent the verification email.

  

  

isAlreadyVerified -> (boolean)

  

   ``True`` if the email address for the registrant contact has already been verified, and ``false`` otherwise. If the email address has already been verified, we don't send another confirmation email.

  

  

