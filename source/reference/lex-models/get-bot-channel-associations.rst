[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models get-bot-channel-associations:


****************************
get-bot-channel-associations
****************************



===========
Description
===========



Returns a list of all of the channels associated with the specified bot. 

 

The ``get-bot-channel-associations`` operation requires permissions for the ``lex:GetBotChannelAssociations`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/GetBotChannelAssociations>`_


========
Synopsis
========

::

    get-bot-channel-associations
  --bot-name <value>
  --bot-alias <value>
  [--next-token <value>]
  [--max-results <value>]
  [--name-contains <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bot-name`` (string)


  The name of the Amazon Lex bot in the association.

  

``--bot-alias`` (string)


  An alias pointing to the specific version of the Amazon Lex bot to which this association is being made.

  

``--next-token`` (string)


  A pagination token for fetching the next page of associations. If the response to this call is truncated, Amazon Lex returns a pagination token in the response. To fetch the next page of associations, specify the pagination token in the next request. 

  

``--max-results`` (integer)


  The maximum number of associations to return in the response. The default is 50. 

  

``--name-contains`` (string)


  Substring to match in channel association names. An association will be returned if any part of its name matches the substring. For example, "xyz" matches both "xyzabc" and "abcxyz." To return all bot channel associations, use a hyphen ("-") as the ``nameContains`` parameter.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

botChannelAssociations -> (list)

  

  An array of objects, one for each association, that provides information about the Amazon Lex bot and its association with the channel. 

  

  (structure)

    

    Represents an association between an Amazon Lex bot and an external messaging platform.

    

    name -> (string)

      

      The name of the association between the bot and the channel. 

      

      

    description -> (string)

      

      A text description of the association you are creating. 

      

      

    botAlias -> (string)

      

      An alias pointing to the specific version of the Amazon Lex bot to which this association is being made. 

      

      

    botName -> (string)

      

      The name of the Amazon Lex bot to which this association is being made. 

       

      .. note::

         

        Currently, Amazon Lex supports associations with Facebook and Slack, and Twilio.

         

      

      

    createdDate -> (timestamp)

      

      The date that the association between the Amazon Lex bot and the channel was created. 

      

      

    type -> (string)

      

      Specifies the type of association by indicating the type of channel being established between the Amazon Lex bot and the external messaging platform.

      

      

    botConfiguration -> (map)

      

      Provides information necessary to communicate with the messaging platform. 

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    

  

nextToken -> (string)

  

  A pagination token that fetches the next page of associations. If the response to this call is truncated, Amazon Lex returns a pagination token in the response. To fetch the next page of associations, specify the pagination token in the next request. 

  

  

