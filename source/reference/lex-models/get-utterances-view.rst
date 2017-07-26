[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models get-utterances-view:


*******************
get-utterances-view
*******************



===========
Description
===========



Use the ``get-utterances-view`` operation to get information about the utterances that your users have made to your bot. You can use this list to tune the utterances that your bot responds to.

 

For example, say that you have created a bot to order flowers. After your users have used your bot for a while, use the ``get-utterances-view`` operation to see the requests that they have made and whether they have been successful. You might find that the utterance "I want flowers" is not being recognized. You could add this utterance to the ``OrderFlowers`` intent so that your bot recognizes that utterance.

 

After you publish a new version of a bot, you can get information about the old version and the new so that you can compare the performance across the two versions. 

 

Data is available for the last 15 days. You can request information for up to 5 versions in each request. The response contains information about a maximum of 100 utterances for each version.

 

If the bot's ``childDirected`` field is set to ``true`` , utterances for the bot are not stored and cannot be retrieved with the ``get-utterances-view`` operation. For more information, see  put-bot .

 

This operation requires permissions for the ``lex:GetUtterancesView`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/GetUtterancesView>`_


========
Synopsis
========

::

    get-utterances-view
  --bot-name <value>
  --bot-versions <value>
  --status-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bot-name`` (string)


  The name of the bot for which utterance information should be returned.

  

``--bot-versions`` (list)


  An array of bot versions for which utterance information should be returned. The limit is 5 versions per request.

  



Syntax::

  "string" "string" ...



``--status-type`` (string)


  To return utterances that were recognized and handled, use``Detected`` . To return utterances that were not recognized, use ``Missed`` .

  

  Possible values:

  
  *   ``Detected``

  
  *   ``Missed``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

botName -> (string)

  

  The name of the bot for which utterance information was returned.

  

  

utterances -> (list)

  

  An array of  UtteranceList objects, each containing a list of  UtteranceData objects describing the utterances that were processed by your bot. The response contains a maximum of 100 ``UtteranceData`` objects for each version.

  

  (structure)

    

    Provides a list of utterances that have been made to a specific version of your bot. The list contains a maximum of 100 utterances.

    

    botVersion -> (string)

      

      The version of the bot that processed the list.

      

      

    utterances -> (list)

      

      One or more  UtteranceData objects that contain information about the utterances that have been made to a bot. The maximum number of object is 100.

      

      (structure)

        

        Provides information about a single utterance that was made to your bot. 

        

        utteranceString -> (string)

          

          The text that was entered by the user or the text representation of an audio clip.

          

          

        count -> (integer)

          

          The number of times that the utterance was processed.

          

          

        distinctUsers -> (integer)

          

          The total number of individuals that used the utterance.

          

          

        firstUtteredDate -> (timestamp)

          

          The date that the utterance was first recorded.

          

          

        lastUtteredDate -> (timestamp)

          

          The date that the utterance was last recorded.

          

          

        

      

    

  

