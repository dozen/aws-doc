[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models delete-utterances:


*****************
delete-utterances
*****************



===========
Description
===========



Deletes stored utterances.

 

Amazon Lex stores the utterances that users send to your bot unless the ``childDirected`` field in the bot is set to ``true`` . Utterances are stored for 15 days for use with the  get-utterances-view operation, and then stored indefinately for use in improving the ability of your bot to respond to user input.

 

Use the ``DeleteStoredUtterances`` operation to manually delete stored utterances for a specific user.

 

This operation requires permissions for the ``lex:DeleteUtterances`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/DeleteUtterances>`_


========
Synopsis
========

::

    delete-utterances
  --bot-name <value>
  --user-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bot-name`` (string)


  The name of the bot that stored the utterances.

  

``--user-id`` (string)


  The unique identifier for the user that made the utterances. This is the user ID that was sent in the `PostContent <http://docs.aws.amazon.com/lex/latest/dg/API_runtime_PostContent.html>`_ or `PostText <http://docs.aws.amazon.com/lex/latest/dg/API_runtime_PostText.html>`_ operation request that contained the utterance.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None