[ :ref:`aws <cli:aws>` . :ref:`cloudsearch <cli:aws cloudsearch>` ]

.. _cli:aws cloudsearch define-suggester:


****************
define-suggester
****************



===========
Description
===========



Configures a suggester for a domain. A suggester enables you to display possible matches before users finish typing their queries. When you configure a suggester, you must specify the name of the text field you want to search for possible matches and a unique name for the suggester. For more information, see `Getting Search Suggestions`_ in the *Amazon CloudSearch Developer Guide* .



========
Synopsis
========

::

    define-suggester
  --domain-name <value>
  --suggester <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  A string that represents the name of a domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

  

``--suggester`` (structure)


  Configuration information for a search suggester. Each suggester has a unique name and specifies the text field you want to use for suggestions. The following options can be configured for a suggester: ``FuzzyMatching`` , ``SortExpression`` . 

  



Shorthand Syntax::

    SuggesterName=string,DocumentSuggesterOptions={SourceField=string,FuzzyMatching=string,SortExpression=string}




JSON Syntax::

  {
    "SuggesterName": "string",
    "DocumentSuggesterOptions": {
      "SourceField": "string",
      "FuzzyMatching": "none"|"low"|"high",
      "SortExpression": "string"
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Suggester -> (structure)

  

  The value of a ``suggester`` and its current status.

  

  Options -> (structure)

    

    Configuration information for a search suggester. Each suggester has a unique name and specifies the text field you want to use for suggestions. The following options can be configured for a suggester: ``FuzzyMatching`` , ``SortExpression`` . 

    

    SuggesterName -> (string)

      

      Names must begin with a letter and can contain the following characters: a-z (lowercase), 0-9, and _ (underscore).

      

      

    DocumentSuggesterOptions -> (structure)

      

      Options for a search suggester.

      

      SourceField -> (string)

        

        The name of the index field you want to use for suggestions. 

        

        

      FuzzyMatching -> (string)

        

        The level of fuzziness allowed when suggesting matches for a string: ``none`` , ``low`` , or ``high`` . With none, the specified string is treated as an exact prefix. With low, suggestions must differ from the specified string by no more than one character. With high, suggestions can differ by up to two characters. The default is none. 

        

        

      SortExpression -> (string)

        

        An expression that computes a score for each suggestion to control how they are sorted. The scores are rounded to the nearest integer, with a floor of 0 and a ceiling of 2^31-1. A document's relevance score is not computed for suggestions, so sort expressions cannot reference the ``_score`` value. To sort suggestions using a numeric field or existing expression, simply specify the name of the field or expression. If no expression is configured for the suggester, the suggestions are sorted with the closest matches listed first.

        

        

      

    

  Status -> (structure)

    

    The status of domain configuration option.

    

    CreationDate -> (timestamp)

      

      A timestamp for when this option was created.

      

      

    UpdateDate -> (timestamp)

      

      A timestamp for when this option was last updated.

      

      

    UpdateVersion -> (integer)

      

      A unique integer that indicates when this option was last updated.

      

      

    State -> (string)

      

      The state of processing a change to an option. Possible values:

       

       
      * ``RequiresIndexDocuments`` : the option's latest value will not be deployed until  index-documents has been called and indexing is complete.
       
      * ``Processing`` : the option's latest value is in the process of being activated. 
       
      * ``Active`` : the option's latest value is completely deployed.
       
      * ``FailedToValidate`` : the option value is not compatible with the domain's data and cannot be used to index the data. You must either modify the option value or update or remove the incompatible documents.
       

      

      

    PendingDeletion -> (boolean)

      

      Indicates that the option will be deleted once processing is complete.

      

      

    

  



.. _Getting Search Suggestions: http://docs.aws.amazon.com/cloudsearch/latest/developerguide/getting-suggestions.html
