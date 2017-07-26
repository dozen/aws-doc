[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 get-geo-location:


****************
get-geo-location
****************



===========
Description
===========



To retrieve a single geo location, send a ``GET`` request to the ``/*Route 53 API version* /geolocation`` resource with one of these options: continentcode | countrycode | countrycode and subdivisioncode.



========
Synopsis
========

::

    get-geo-location
  [--continent-code <value>]
  [--country-code <value>]
  [--subdivision-code <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--continent-code`` (string)


  The code for a continent geo location. Note: only continent locations have a continent code.

   

  Valid values: ``AF`` | ``AN`` | ``AS`` | ``EU`` | ``OC`` | ``NA`` | ``SA`` 

   

  Constraint: Specifying ``ContinentCode`` with either ``CountryCode`` or ``SubdivisionCode`` returns an  InvalidInput error.

  

``--country-code`` (string)


  The code for a country geo location. The default location uses '*' for the country code and will match all locations that are not matched by a geo location.

   

  The default geo location uses a ``*`` for the country code. All other country codes follow the ISO 3166 two-character code.

  

``--subdivision-code`` (string)


  The code for a country's subdivision (e.g., a province of Canada). A subdivision code is only valid with the appropriate country code.

   

  Constraint: Specifying ``SubdivisionCode`` without ``CountryCode`` returns an  InvalidInput error.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

GeoLocationDetails -> (structure)

  

  A complex type that contains the information about the specified geo location.

  

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

    

    

  

