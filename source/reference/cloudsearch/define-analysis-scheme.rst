[ :ref:`aws <cli:aws>` . :ref:`cloudsearch <cli:aws cloudsearch>` ]

.. _cli:aws cloudsearch define-analysis-scheme:


**********************
define-analysis-scheme
**********************



===========
Description
===========



Configures an analysis scheme that can be applied to a ``text`` or ``text-array`` field to define language-specific text processing options. For more information, see `Configuring Analysis Schemes <http://docs.aws.amazon.com/cloudsearch/latest/developerguide/configuring-analysis-schemes.html>`_ in the *Amazon CloudSearch Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudsearch-2013-01-01/DefineAnalysisScheme>`_


========
Synopsis
========

::

    define-analysis-scheme
  --domain-name <value>
  --analysis-scheme <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  A string that represents the name of a domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

  

``--analysis-scheme`` (structure)


  Configuration information for an analysis scheme. Each analysis scheme has a unique name and specifies the language of the text to be processed. The following options can be configured for an analysis scheme: ``Synonyms`` , ``Stopwords`` , ``StemmingDictionary`` , ``JapaneseTokenizationDictionary`` and ``AlgorithmicStemming`` .

  



Shorthand Syntax::

    AnalysisSchemeName=string,AnalysisSchemeLanguage=string,AnalysisOptions={Synonyms=string,Stopwords=string,StemmingDictionary=string,JapaneseTokenizationDictionary=string,AlgorithmicStemming=string}




JSON Syntax::

  {
    "AnalysisSchemeName": "string",
    "AnalysisSchemeLanguage": "ar"|"bg"|"ca"|"cs"|"da"|"de"|"el"|"en"|"es"|"eu"|"fa"|"fi"|"fr"|"ga"|"gl"|"he"|"hi"|"hu"|"hy"|"id"|"it"|"ja"|"ko"|"lv"|"mul"|"nl"|"no"|"pt"|"ro"|"ru"|"sv"|"th"|"tr"|"zh-Hans"|"zh-Hant",
    "AnalysisOptions": {
      "Synonyms": "string",
      "Stopwords": "string",
      "StemmingDictionary": "string",
      "JapaneseTokenizationDictionary": "string",
      "AlgorithmicStemming": "none"|"minimal"|"light"|"full"
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

AnalysisScheme -> (structure)

  

  The status and configuration of an ``analysis-scheme`` .

  

  Options -> (structure)

    

    Configuration information for an analysis scheme. Each analysis scheme has a unique name and specifies the language of the text to be processed. The following options can be configured for an analysis scheme: ``Synonyms`` , ``Stopwords`` , ``StemmingDictionary`` , ``JapaneseTokenizationDictionary`` and ``AlgorithmicStemming`` .

    

    AnalysisSchemeName -> (string)

      

      Names must begin with a letter and can contain the following characters: a-z (lowercase), 0-9, and _ (underscore).

      

      

    AnalysisSchemeLanguage -> (string)

      

      An `IETF RFC 4646 <http://tools.ietf.org/html/rfc4646>`_ language code or ``mul`` for multiple languages.

      

      

    AnalysisOptions -> (structure)

      

      Synonyms, stopwords, and stemming options for an analysis scheme. Includes tokenization dictionary for Japanese.

      

      Synonyms -> (string)

        

        A JSON object that defines synonym groups and aliases. A synonym group is an array of arrays, where each sub-array is a group of terms where each term in the group is considered a synonym of every other term in the group. The aliases value is an object that contains a collection of string:value pairs where the string specifies a term and the array of values specifies each of the aliases for that term. An alias is considered a synonym of the specified term, but the term is not considered a synonym of the alias. For more information about specifying synonyms, see `Synonyms <http://docs.aws.amazon.com/cloudsearch/latest/developerguide/configuring-analysis-schemes.html#synonyms>`_ in the *Amazon CloudSearch Developer Guide* .

        

        

      Stopwords -> (string)

        

        A JSON array of terms to ignore during indexing and searching. For example, ``["a", "an", "the", "of"]`` . The stopwords dictionary must explicitly list each word you want to ignore. Wildcards and regular expressions are not supported. 

        

        

      StemmingDictionary -> (string)

        

        A JSON object that contains a collection of string:value pairs that each map a term to its stem. For example, ``{"term1": "stem1", "term2": "stem2", "term3": "stem3"}`` . The stemming dictionary is applied in addition to any algorithmic stemming. This enables you to override the results of the algorithmic stemming to correct specific cases of overstemming or understemming. The maximum size of a stemming dictionary is 500 KB.

        

        

      JapaneseTokenizationDictionary -> (string)

        

        A JSON array that contains a collection of terms, tokens, readings and part of speech for Japanese Tokenizaiton. The Japanese tokenization dictionary enables you to override the default tokenization for selected terms. This is only valid for Japanese language fields.

        

        

      AlgorithmicStemming -> (string)

        

        The level of algorithmic stemming to perform: ``none`` , ``minimal`` , ``light`` , or ``full`` . The available levels vary depending on the language. For more information, see `Language Specific Text Processing Settings <http://docs.aws.amazon.com/cloudsearch/latest/developerguide/text-processing.html#text-processing-settings>`_ in the *Amazon CloudSearch Developer Guide*  

        

        

      

    

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

      

      

    

  

