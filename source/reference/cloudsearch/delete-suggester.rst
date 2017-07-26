[ :ref:`aws <cli:aws>` . :ref:`cloudsearch <cli:aws cloudsearch>` ]

.. _cli:aws cloudsearch delete-suggester:


****************
delete-suggester
****************



===========
Description
===========



Deletes a suggester. For more information, see `Getting Search Suggestions <http://docs.aws.amazon.com/cloudsearch/latest/developerguide/getting-suggestions.html>`_ in the *Amazon CloudSearch Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudsearch-2013-01-01/DeleteSuggester>`_


========
Synopsis
========

::

    delete-suggester
  --domain-name <value>
  --suggester-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  A string that represents the name of a domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

  

``--suggester-name`` (string)


  Specifies the name of the suggester you want to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Suggester -> (structure)

  

  The status of the suggester being deleted.

  

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

      

      

    

  

