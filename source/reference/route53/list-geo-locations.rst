[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-geo-locations:


******************
list-geo-locations
******************



===========
Description
===========



Retrieves a list of supported geo locations.

 

Countries are listed first, and continents are listed last. If Amazon Route 53 supports subdivisions for a country (for example, states or provinces), the subdivisions for that country are listed in alphabetical order immediately after the corresponding country.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/ListGeoLocations>`_


========
Synopsis
========

::

    list-geo-locations
  [--start-continent-code <value>]
  [--start-country-code <value>]
  [--start-subdivision-code <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--start-continent-code`` (string)


  The code for the continent with which you want to start listing locations that Amazon Route 53 supports for geolocation. If Amazon Route 53 has already returned a page or more of results, if ``IsTruncated`` is true, and if ``NextContinentCode`` from the previous response has a value, enter that value in ``StartContinentCode`` to return the next page of results.

   

  Include ``StartContinentCode`` only if you want to list continents. Don't include ``StartContinentCode`` when you're listing countries or countries with their subdivisions.

  

``--start-country-code`` (string)


  The code for the country with which you want to start listing locations that Amazon Route 53 supports for geolocation. If Amazon Route 53 has already returned a page or more of results, if ``IsTruncated`` is ``true`` , and if ``NextCountryCode`` from the previous response has a value, enter that value in ``StartCountryCode`` to return the next page of results.

   

  Amazon Route 53 uses the two-letter country codes that are specified in `ISO standard 3166-1 alpha-2 <https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2>`_ .

  

``--start-subdivision-code`` (string)


  The code for the subdivision (for example, state or province) with which you want to start listing locations that Amazon Route 53 supports for geolocation. If Amazon Route 53 has already returned a page or more of results, if ``IsTruncated`` is ``true`` , and if ``NextSubdivisionCode`` from the previous response has a value, enter that value in ``StartSubdivisionCode`` to return the next page of results.

   

  To list subdivisions of a country, you must include both ``StartCountryCode`` and ``StartSubdivisionCode`` .

  

``--max-items`` (string)


  (Optional) The maximum number of geolocations to be included in the response body for this request. If more than ``MaxItems`` geolocations remain to be listed, then the value of the ``IsTruncated`` element in the response is ``true`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

GeoLocationDetailsList -> (list)

  

  A complex type that contains one ``GeoLocationDetails`` element for each location that Amazon Route 53 supports for geolocation.

  

  (structure)

    

    A complex type that contains the codes and full continent, country, and subdivision names for the specified ``geolocation`` code.

    

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

      

      

    

  

IsTruncated -> (boolean)

  

  A value that indicates whether more locations remain to be listed after the last location in this response. If so, the value of ``IsTruncated`` is ``true`` . To get more values, submit another request and include the values of ``NextContinentCode`` , ``NextCountryCode`` , and ``NextSubdivisionCode`` in the ``StartContinentCode`` , ``StartCountryCode`` , and ``StartSubdivisionCode`` , as applicable.

  

  

NextContinentCode -> (string)

  

  If ``IsTruncated`` is ``true`` , you can make a follow-up request to display more locations. Enter the value of ``NextContinentCode`` in the ``StartContinentCode`` parameter in another ``list-geo-locations`` request.

  

  

NextCountryCode -> (string)

  

  If ``IsTruncated`` is ``true`` , you can make a follow-up request to display more locations. Enter the value of ``NextCountryCode`` in the ``StartCountryCode`` parameter in another ``list-geo-locations`` request.

  

  

NextSubdivisionCode -> (string)

  

  If ``IsTruncated`` is ``true`` , you can make a follow-up request to display more locations. Enter the value of ``NextSubdivisionCode`` in the ``StartSubdivisionCode`` parameter in another ``list-geo-locations`` request.

  

  

MaxItems -> (string)

  

  The value that you specified for ``MaxItems`` in the request.

  

  

