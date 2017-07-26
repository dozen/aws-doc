[ :ref:`aws <cli:aws>` . :ref:`cloudsearchdomain <cli:aws cloudsearchdomain>` ]

.. _cli:aws cloudsearchdomain suggest:


*******
suggest
*******



===========
Description
===========



Retrieves autocomplete suggestions for a partial query string. You can use suggestions enable you to display likely matches before users finish typing. In Amazon CloudSearch, suggestions are based on the contents of a particular text field. When you request suggestions, Amazon CloudSearch finds all of the documents whose values in the suggester field start with the specified query string. The beginning of the field must match the query string to be considered a match. 

 

For more information about configuring suggesters and retrieving suggestions, see `Getting Suggestions`_ in the *Amazon CloudSearch Developer Guide* . 

 

The endpoint for submitting ``suggest`` requests is domain-specific. You submit suggest requests to a domain's search endpoint. To get the search endpoint for your domain, use the Amazon CloudSearch configuration service ``DescribeDomains`` action. A domain's endpoints are also displayed on the domain dashboard in the Amazon CloudSearch console. 



========
Synopsis
========

::

    suggest
  --suggester <value>
  [--size <value>]
  --suggest-query <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--suggester`` (string)


  Specifies the name of the suggester to use to find suggested matches.

  

``--size`` (long)


  Specifies the maximum number of suggestions to return. 

  

``--suggest-query`` (string)


  Specifies the string for which you want to get suggestions.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

status -> (structure)

  

  The status of a ``SuggestRequest`` . Contains the resource ID (``rid`` ) and how long it took to process the request (``timems`` ).

  

  timems -> (long)

    

    How long it took to process the request, in milliseconds.

    

    

  rid -> (string)

    

    The encrypted resource ID for the request.

    

    

  

suggest -> (structure)

  

  Container for the matching search suggestion information.

  

  query -> (string)

    

    The query string specified in the suggest request.

    

    

  found -> (long)

    

    The number of documents that were found to match the query string.

    

    

  suggestions -> (list)

    

    The documents that match the query string.

    

    (structure)

      

      An autocomplete suggestion that matches the query string specified in a ``SuggestRequest`` . 

      

      suggestion -> (string)

        

        The string that matches the query string specified in the ``SuggestRequest`` . 

        

        

      score -> (long)

        

        The relevance score of a suggested match.

        

        

      id -> (string)

        

        The document ID of the suggested document.

        

        

      

    

  



.. _Getting Suggestions: http://docs.aws.amazon.com/cloudsearch/latest/developerguide/getting-suggestions.html
