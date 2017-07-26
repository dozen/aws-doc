[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains check-domain-availability:


*************************
check-domain-availability
*************************



===========
Description
===========



This operation checks the availability of one domain name. Note that if the availability status of a domain is pending, you must submit another request to determine the availability of the domain name.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53domains-2014-05-15/CheckDomainAvailability>`_


========
Synopsis
========

::

    check-domain-availability
  --domain-name <value>
  [--idn-lang-code <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The name of the domain that you want to get availability for.

   

  Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Internationalized Domain Names are not supported.

  

``--idn-lang-code`` (string)


  Reserved for future use.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Availability -> (string)

  

  Whether the domain name is available for registering.

   

  .. note::

     

    You can only register domains designated as ``AVAILABLE`` .

     

   

  Valid values:

    AVAILABLE  

  The domain name is available.

    AVAILABLE_RESERVED  

  The domain name is reserved under specific conditions.

    AVAILABLE_PREORDER  

  The domain name is available and can be preordered.

    DONT_KNOW  

  The TLD registry didn't reply with a definitive answer about whether the domain name is available. Amazon Route 53 can return this response for a variety of reasons, for example, the registry is performing maintenance. Try again later.

    PENDING  

  The TLD registry didn't return a response in the expected amount of time. When the response is delayed, it usually takes just a few extra seconds. You can resubmit the request immediately.

    RESERVED  

  The domain name has been reserved for another person or organization.

    UNAVAILABLE  

  The domain name is not available.

    UNAVAILABLE_PREMIUM  

  The domain name is not available.

    UNAVAILABLE_RESTRICTED  

  The domain name is forbidden.

    

  

