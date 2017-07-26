[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models delete-intent:


*************
delete-intent
*************



===========
Description
===========



Deletes all versions of the intent, including the ``$LATEST`` version. To delete a specific version of the intent, use the  delete-intent-version operation.

 

You can delete a version of an intent only if it is not referenced. To delete an intent that is referred to in one or more bots (see  how-it-works ), you must remove those references first. 

 

.. note::

   

  If you get the ``ResourceInUseException`` exception, it provides an example reference that shows where the intent is referenced. To remove the reference to the intent, either update the bot or delete it. If you get the same exception when you attempt to delete the intent again, repeat until the intent has no references and the call to ``delete-intent`` is successful. 

   

 

This operation requires permission for the ``lex:DeleteIntent`` action. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/DeleteIntent>`_


========
Synopsis
========

::

    delete-intent
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the intent. The name is case sensitive. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None