[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-geo-locations:


******************
list-geo-locations
******************



===========
Description
===========



To retrieve a list of supported geo locations, send a ``GET`` request to the ``/*Route 53 API version* /geolocations`` resource. The response to this request includes a ``GeoLocationDetailsList`` element with zero, one, or multiple ``GeoLocationDetails`` child elements. The list is sorted by country code, and then subdivision code, followed by continents at the end of the list. 

 

By default, the list of geo locations is displayed on a single page. You can control the length of the page that is displayed by using the ``MaxItems`` parameter. If the list is truncated, ``IsTruncated`` will be set to *true* and a combination of ``NextContinentCode, NextCountryCode, NextSubdivisionCode`` will be populated. You can pass these as parameters to ``StartContinentCode, StartCountryCode, StartSubdivisionCode`` to control the geo location that the list begins with. 



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
  [--generate-cli-skeleton]




=======
Options
=======

``--start-continent-code`` (string)


  The first continent code in the lexicographic ordering of geo locations that you want the ``list-geo-locations`` request to list. For non-continent geo locations, this should be null.

   

  Valid values: ``AF`` | ``AN`` | ``AS`` | ``EU`` | ``OC`` | ``NA`` | ``SA`` 

   

  Constraint: Specifying ``ContinentCode`` with either ``CountryCode`` or ``SubdivisionCode`` returns an  InvalidInput error.

  

``--start-country-code`` (string)


  The first country code in the lexicographic ordering of geo locations that you want the ``list-geo-locations`` request to list.

   

  The default geo location uses a ``*`` for the country code. All other country codes follow the ISO 3166 two-character code.

  

``--start-subdivision-code`` (string)


  The first subdivision code in the lexicographic ordering of geo locations that you want the ``list-geo-locations`` request to list.

   

  Constraint: Specifying ``SubdivisionCode`` without ``CountryCode`` returns an  InvalidInput error.

  

``--max-items`` (string)


  The maximum number of geo locations you want in the response body.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

GeoLocationDetailsList -> (list)

  

  A complex type that contains information about the geo locations that are returned by the request.

  

  (structure)

    

    A complex type that contains information about a ``GeoLocation`` .

    

    ContinentCode -> (string)

      

      The code for a continent geo location. Note: only continent locations have a continent code.

      

      

    ContinentName -> (string)

      

      The name of the continent. This element is only present if ``ContinentCode`` is also present.

      

      

    CountryCode -> (string)

      

      The code for a country geo location. The default location uses '*' for the country code and will match all locations that are not matched by a geo location.

       

      The default geo location uses a ``*`` for the country code. All other country codes follow the ISO 3166 two-character code.

      

      

    CountryName -> (string)

      

      The name of the country. This element is only present if ``CountryCode`` is also present.

      

      

    SubdivisionCode -> (string)

      

      The code for a country's subdivision (e.g., a province of Canada). A subdivision code is only valid with the appropriate country code.

      

      

    SubdivisionName -> (string)

      

      The name of the subdivision. This element is only present if ``SubdivisionCode`` is also present.

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more geo locations to be listed. If your results were truncated, you can make a follow-up request for the next page of results by using the values included in the  ListGeoLocationsResponse$NextContinentCode ,  ListGeoLocationsResponse$NextCountryCode and  ListGeoLocationsResponse$NextSubdivisionCode elements.

   

  Valid Values: ``true`` | ``false`` 

  

  

NextContinentCode -> (string)

  

  If the results were truncated, the continent code of the next geo location in the list. This element is present only if  ListGeoLocationsResponse$IsTruncated is true and the next geo location to list is a continent location. 

  

  

NextCountryCode -> (string)

  

  If the results were truncated, the country code of the next geo location in the list. This element is present only if  ListGeoLocationsResponse$IsTruncated is true and the next geo location to list is not a continent location. 

  

  

NextSubdivisionCode -> (string)

  

  If the results were truncated, the subdivision code of the next geo location in the list. This element is present only if  ListGeoLocationsResponse$IsTruncated is true and the next geo location has a subdivision. 

  

  

MaxItems -> (string)

  

  The maximum number of records you requested. The maximum value of ``MaxItems`` is 100.

  

  

