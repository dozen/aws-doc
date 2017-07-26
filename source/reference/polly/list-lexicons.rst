[ :ref:`aws <cli:aws>` . :ref:`polly <cli:aws polly>` ]

.. _cli:aws polly list-lexicons:


*************
list-lexicons
*************



===========
Description
===========



Returns a list of pronunciation lexicons stored in an AWS Region. For more information, see `Managing Lexicons <http://docs.aws.amazon.com/polly/latest/dg/managing-lexicons.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/polly-2016-06-10/ListLexicons>`_


========
Synopsis
========

::

    list-lexicons
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  An opaque pagination token returned from previous ``list-lexicons`` operation. If present, indicates where to continue the list of lexicons.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Lexicons -> (list)

  

  A list of lexicon names and attributes.

  

  (structure)

    

    Describes the content of the lexicon.

    

    Name -> (string)

      

      Name of the lexicon.

      

      

    Attributes -> (structure)

      

      Provides lexicon metadata.

      

      Alphabet -> (string)

        

        Phonetic alphabet used in the lexicon. Valid values are ``ipa`` and ``x-sampa`` .

        

        

      LanguageCode -> (string)

        

        Language code that the lexicon applies to. A lexicon with a language code such as "en" would be applied to all English languages (en-GB, en-US, en-AUS, en-WLS, and so on.

        

        

      LastModified -> (timestamp)

        

        Date lexicon was last modified (a timestamp value).

        

        

      LexiconArn -> (string)

        

        Amazon Resource Name (ARN) of the lexicon.

        

        

      LexemesCount -> (integer)

        

        Number of lexemes in the lexicon.

        

        

      Size -> (integer)

        

        Total size of the lexicon, in characters.

        

        

      

    

  

NextToken -> (string)

  

  The pagination token to use in the next request to continue the listing of lexicons. ``next-token`` is returned only if the response is truncated.

  

  

