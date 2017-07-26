[ :ref:`aws <cli:aws>` . :ref:`polly <cli:aws polly>` ]

.. _cli:aws polly get-lexicon:


***********
get-lexicon
***********



===========
Description
===========



Returns the content of the specified pronunciation lexicon stored in an AWS Region. For more information, see `Managing Lexicons <http://docs.aws.amazon.com/polly/latest/dg/managing-lexicons.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/polly-2016-06-10/GetLexicon>`_


========
Synopsis
========

::

    get-lexicon
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  Name of the lexicon.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Lexicon -> (structure)

  

  Lexicon object that provides name and the string content of the lexicon. 

  

  Content -> (string)

    

    Lexicon content in string format. The content of a lexicon must be in PLS format.

    

    

  Name -> (string)

    

    Name of the lexicon.

    

    

  

LexiconAttributes -> (structure)

  

  Metadata of the lexicon, including phonetic alphabetic used, language code, lexicon ARN, number of lexemes defined in the lexicon, and size of lexicon in bytes.

  

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

    

    

  

