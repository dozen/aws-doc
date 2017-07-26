[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 get-geo-location:


****************
get-geo-location
****************



===========
Description
===========



Gets information about whether a specified geographic location is supported for Amazon Route 53 geolocation resource record sets.

 

Use the following syntax to determine whether a continent is supported for geolocation:

 

 ``GET /2013-04-01/geolocation?ContinentCode=*two-letter abbreviation for a continent* ``  

 

Use the following syntax to determine whether a country is supported for geolocation:

 

 ``GET /2013-04-01/geolocation?CountryCode=*two-character country code* ``  

 

Use the following syntax to determine whether a subdivision of a country is supported for geolocation:

 

 ``GET /2013-04-01/geolocation?CountryCode=*two-character country code* SubdivisionCode=*subdivision code* ``  



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/GetGeoLocation>`_


========
Synopsis
========

::

    get-geo-location
  [--continent-code <value>]
  [--country-code <value>]
  [--subdivision-code <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--continent-code`` (string)


  Amazon Route 53 supports the following continent codes:

   

   
  * **AF** : Africa 
   
  * **AN** : Antarctica 
   
  * **AS** : Asia 
   
  * **EU** : Europe 
   
  * **OC** : Oceania 
   
  * **NA** : North America 
   
  * **SA** : South America 
   

  

``--country-code`` (string)


  Amazon Route 53 uses the two-letter country codes that are specified in `ISO standard 3166-1 alpha-2 <https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2>`_ .

  

``--subdivision-code`` (string)


  Amazon Route 53 uses the one- to three-letter subdivision codes that are specified in `ISO standard 3166-1 alpha-2 <https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2>`_ . Amazon Route 53 doesn't support subdivision codes for all countries. If you specify ``SubdivisionCode`` , you must also specify ``CountryCode`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

GeoLocationDetails -> (structure)

  

  A complex type that contains the codes and full continent, country, and subdivision names for the specified geolocation code.

  

  ContinentCode -> (string)

    

    The two-letter code for the continent.

    

    

  ContinentName -> (string)

    

    The full name of the continent.

    

    

  CountryCode -> (string)

    

    The two-letter code for the country.

    

    

  CountryName -> (string)

    

    The name of the country.

    

    

  SubdivisionCode -> (string)

    

    The code for the subdivision, for example, a state in the United States or a province in Canada.

    

    

  SubdivisionName -> (string)

    

    The full name of the subdivision, for example, a state in the United States or a province in Canada.

    

    

  

