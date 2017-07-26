[ :ref:`aws <cli:aws>` . :ref:`polly <cli:aws polly>` ]

.. _cli:aws polly synthesize-speech:


*****************
synthesize-speech
*****************



===========
Description
===========



Synthesizes UTF-8 input, plain text or SSML, to a stream of bytes. SSML input must be valid, well-formed SSML. Some alphabets might not be available with all the voices (for example, Cyrillic might not be read at all by English voices) unless phoneme mapping is used. For more information, see `How it Works <http://docs.aws.amazon.com/polly/latest/dg/how-text-to-speech-works.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/polly-2016-06-10/SynthesizeSpeech>`_


========
Synopsis
========

::

    synthesize-speech
  [--lexicon-names <value>]
  --output-format <value>
  [--sample-rate <value>]
  [--speech-mark-types <value>]
  --text <value>
  [--text-type <value>]
  --voice-id <value>
  outfile <value>




=======
Options
=======

``--lexicon-names`` (list)


  List of one or more pronunciation lexicon names you want the service to apply during synthesis. Lexicons are applied only if the language of the lexicon is the same as the language of the voice. For information about storing lexicons, see `put-lexicon <http://docs.aws.amazon.com/polly/latest/dg/API_PutLexicon.html>`_ .

  



Syntax::

  "string" "string" ...



``--output-format`` (string)


  The format in which the returned output will be encoded. For audio stream, this will be mp3, ogg_vorbis, or pcm. For speech marks, this will be json. 

  

  Possible values:

  
  *   ``json``

  
  *   ``mp3``

  
  *   ``ogg_vorbis``

  
  *   ``pcm``

  

  

``--sample-rate`` (string)


  The audio frequency specified in Hz. 

   

  The valid values for ``mp3`` and ``ogg_vorbis`` are "8000", "16000", and "22050". The default value is "22050". 

   

  Valid values for ``pcm`` are "8000" and "16000" The default value is "16000". 

  

``--speech-mark-types`` (list)


  The type of speech marks returned for the input text.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    sentence
    ssml
    viseme
    word





``--text`` (string)


  Input text to synthesize. If you specify ``ssml`` as the ``text-type`` , follow the SSML format for the input text. 

  

``--text-type`` (string)


  Specifies whether the input text is plain text or SSML. The default value is plain text. For more information, see `Using SSML <http://docs.aws.amazon.com/polly/latest/dg/ssml.html>`_ .

  

  Possible values:

  
  *   ``ssml``

  
  *   ``text``

  

  

``--voice-id`` (string)


  Voice ID to use for the synthesis. You can get a list of available voice IDs by calling the `describe-voices <http://docs.aws.amazon.com/polly/latest/dg/API_DescribeVoices.html>`_ operation. 

  

  Possible values:

  
  *   ``Geraint``

  
  *   ``Gwyneth``

  
  *   ``Mads``

  
  *   ``Naja``

  
  *   ``Hans``

  
  *   ``Marlene``

  
  *   ``Nicole``

  
  *   ``Russell``

  
  *   ``Amy``

  
  *   ``Brian``

  
  *   ``Emma``

  
  *   ``Raveena``

  
  *   ``Ivy``

  
  *   ``Joanna``

  
  *   ``Joey``

  
  *   ``Justin``

  
  *   ``Kendra``

  
  *   ``Kimberly``

  
  *   ``Salli``

  
  *   ``Conchita``

  
  *   ``Enrique``

  
  *   ``Miguel``

  
  *   ``Penelope``

  
  *   ``Chantal``

  
  *   ``Celine``

  
  *   ``Mathieu``

  
  *   ``Dora``

  
  *   ``Karl``

  
  *   ``Carla``

  
  *   ``Giorgio``

  
  *   ``Mizuki``

  
  *   ``Liv``

  
  *   ``Lotte``

  
  *   ``Ruben``

  
  *   ``Ewa``

  
  *   ``Jacek``

  
  *   ``Jan``

  
  *   ``Maja``

  
  *   ``Ricardo``

  
  *   ``Vitoria``

  
  *   ``Cristiano``

  
  *   ``Ines``

  
  *   ``Carmen``

  
  *   ``Maxim``

  
  *   ``Tatyana``

  
  *   ``Astrid``

  
  *   ``Filiz``

  
  *   ``Vicki``

  

  

``outfile`` (string)
Filename where the content will be saved



======
Output
======

AudioStream -> (blob)

  

  Stream containing the synthesized speech. 

  

  

ContentType -> (string)

  

  Specifies the type audio stream. This should reflect the ``output-format`` parameter in your request. 

   

   
  * If you request ``mp3`` as the ``output-format`` , the ``ContentType`` returned is audio/mpeg.  
   
  * If you request ``ogg_vorbis`` as the ``output-format`` , the ``ContentType`` returned is audio/ogg.  
   
  * If you request ``pcm`` as the ``output-format`` , the ``ContentType`` returned is audio/pcm in a signed 16-bit, 1 channel (mono), little-endian format.  
   
  * If you request ``json`` as the ``output-format`` , the ``ContentType`` returned is audio/json. 
   

   

   

  

  

RequestCharacters -> (integer)

  

  Number of characters synthesized.

  

  

