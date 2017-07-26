[ :ref:`aws <cli:aws>` . :ref:`polly <cli:aws polly>` ]

.. _cli:aws polly describe-voices:


***************
describe-voices
***************



===========
Description
===========



Returns the list of voices that are available for use when requesting speech synthesis. Each voice speaks a specified language, is either male or female, and is identified by an ID, which is the ASCII version of the voice name. 

 

When synthesizing speech ( ``synthesize-speech`` ), you provide the voice ID for the voice you want from the list of voices returned by ``describe-voices`` .

 

For example, you want your news reader application to read news in a specific language, but giving a user the option to choose the voice. Using the ``describe-voices`` operation you can provide the user with a list of available voices to select from.

 

You can optionally specify a language code to filter the available voices. For example, if you specify ``en-US`` , the operation returns a list of all available US English voices. 

 

This operation requires permissions to perform the ``polly:DescribeVoices`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/polly-2016-06-10/DescribeVoices>`_


========
Synopsis
========

::

    describe-voices
  [--language-code <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--language-code`` (string)


  The language identification tag (ISO 639 code for the language name-ISO 3166 country code) for filtering the list of voices returned. If you don't specify this optional parameter, all available voices are returned. 

  

  Possible values:

  
  *   ``cy-GB``

  
  *   ``da-DK``

  
  *   ``de-DE``

  
  *   ``en-AU``

  
  *   ``en-GB``

  
  *   ``en-GB-WLS``

  
  *   ``en-IN``

  
  *   ``en-US``

  
  *   ``es-ES``

  
  *   ``es-US``

  
  *   ``fr-CA``

  
  *   ``fr-FR``

  
  *   ``is-IS``

  
  *   ``it-IT``

  
  *   ``ja-JP``

  
  *   ``nb-NO``

  
  *   ``nl-NL``

  
  *   ``pl-PL``

  
  *   ``pt-BR``

  
  *   ``pt-PT``

  
  *   ``ro-RO``

  
  *   ``ru-RU``

  
  *   ``sv-SE``

  
  *   ``tr-TR``

  

  

``--next-token`` (string)


  An opaque pagination token returned from the previous ``describe-voices`` operation. If present, this indicates where to continue the listing.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Voices -> (list)

  

  A list of voices with their properties.

  

  (structure)

    

    Description of the voice.

    

    Gender -> (string)

      

      Gender of the voice.

      

      

    Id -> (string)

      

      Amazon Polly assigned voice ID. This is the ID that you specify when calling the ``synthesize-speech`` operation.

      

      

    LanguageCode -> (string)

      

      Language code of the voice.

      

      

    LanguageName -> (string)

      

      Human readable name of the language in English.

      

      

    Name -> (string)

      

      Name of the voice (for example, Salli, Kendra, etc.). This provides a human readable voice name that you might display in your application.

      

      

    

  

NextToken -> (string)

  

  The pagination token to use in the next request to continue the listing of voices. ``next-token`` is returned only if the response is truncated.

  

  

