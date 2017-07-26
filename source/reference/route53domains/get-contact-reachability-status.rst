[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains get-contact-reachability-status:


*******************************
get-contact-reachability-status
*******************************



===========
Description
===========



For operations that require confirmation that the email address for the registrant contact is valid, such as registering a new domain, this operation returns information about whether the registrant contact has responded.

 

If you want us to resend the email, use the ``resend-contact-reachability-email`` operation.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53domains-2014-05-15/GetContactReachabilityStatus>`_


========
Synopsis
========

::

    get-contact-reachability-status
  [--domain-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The name of the domain for which you want to know whether the registrant contact has confirmed that the email address is valid.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

domainName -> (string)

  

  The domain name for which you requested the reachability status.

  

  

status -> (string)

  

  Whether the registrant contact has responded. Values include the following:

    PENDING  

  We sent the confirmation email and haven't received a response yet.

    DONE  

  We sent the email and got confirmation from the registrant contact.

    EXPIRED  

  The time limit expired before the registrant contact responded.

    

  

