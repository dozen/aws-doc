[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses get-identity-mail-from-domain-attributes:


****************************************
get-identity-mail-from-domain-attributes
****************************************



===========
Description
===========



Returns the custom MAIL FROM attributes for a list of identities (email addresses and/or domains).

 

This action is throttled at one request per second and can only get custom MAIL FROM attributes for up to 100 identities at a time.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/GetIdentityMailFromDomainAttributes>`_


========
Synopsis
========

::

    get-identity-mail-from-domain-attributes
  --identities <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identities`` (list)


  A list of one or more identities.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

MailFromDomainAttributes -> (map)

  

  A map of identities to custom MAIL FROM attributes.

  

  key -> (string)

    

    

  value -> (structure)

    

    Represents the custom MAIL FROM domain attributes of a verified identity (email address or domain).

    

    MailFromDomain -> (string)

      

      The custom MAIL FROM domain that the identity is configured to use.

      

      

    MailFromDomainStatus -> (string)

      

      The state that indicates whether Amazon SES has successfully read the MX record required for custom MAIL FROM domain setup. If the state is ``Success`` , Amazon SES uses the specified custom MAIL FROM domain when the verified identity sends an email. All other states indicate that Amazon SES takes the action described by ``BehaviorOnMXFailure`` .

      

      

    BehaviorOnMXFailure -> (string)

      

      The action that Amazon SES takes if it cannot successfully read the required MX record when you send an email. A value of ``UseDefaultValue`` indicates that if Amazon SES cannot read the required MX record, it uses amazonses.com (or a subdomain of that) as the MAIL FROM domain. A value of ``RejectMessage`` indicates that if Amazon SES cannot read the required MX record, Amazon SES returns a ``MailFromDomainNotVerified`` error and does not send the email.

       

      The custom MAIL FROM setup states that result in this behavior are ``Pending`` , ``Failed`` , and ``TemporaryFailure`` .

      

      

    

  

