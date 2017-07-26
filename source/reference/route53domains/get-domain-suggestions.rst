[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains get-domain-suggestions:


**********************
get-domain-suggestions
**********************



===========
Description
===========



The get-domain-suggestions operation returns a list of suggested domain names given a string, which can either be a domain name or simply a word or phrase (without spaces).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53domains-2014-05-15/GetDomainSuggestions>`_


========
Synopsis
========

::

    get-domain-suggestions
  --domain-name <value>
  --suggestion-count <value>
  --only-available | --no-only-available
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  A domain name that you want to use as the basis for a list of possible domain names. The domain name must contain a top-level domain (TLD), such as .com, that Amazon Route 53 supports. For a list of TLDs, see `Domains that You Can Register with Amazon Route 53 <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/registrar-tld-list.html>`_ in the *Amazon Route 53 Developer Guide* .

  

``--suggestion-count`` (integer)


  The number of suggested domain names that you want Amazon Route 53 to return.

  

``--only-available`` | ``--no-only-available`` (boolean)


  If ``OnlyAvailable`` is ``true`` , Amazon Route 53 returns only domain names that are available. If ``OnlyAvailable`` is ``false`` , Amazon Route 53 returns domain names without checking whether they're available to be registered. To determine whether the domain is available, you can call ``checkDomainAvailability`` for each suggestion.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SuggestionsList -> (list)

  

  A list of possible domain names. If you specified ``true`` for ``OnlyAvailable`` in the request, the list contains only domains that are available for registration.

  

  (structure)

    

    Information about one suggested domain name.

    

    DomainName -> (string)

      

      A suggested domain name.

      

      

    Availability -> (string)

      

      Whether the domain name is available for registering.

       

      .. note::

         

        You can register only the domains that are designated as ``AVAILABLE`` .

         

       

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

        

      

    

  

