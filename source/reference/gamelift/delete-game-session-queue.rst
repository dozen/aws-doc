[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift delete-game-session-queue:


*************************
delete-game-session-queue
*************************



===========
Description
===========



Deletes a game session queue. This action means that any  start-game-session-placement requests that reference this queue will fail. To delete a queue, specify the queue name.

 

Queue-related operations include:

 

 
*  create-game-session-queue   
 
*  describe-game-session-queues   
 
*  update-game-session-queue   
 
*  delete-game-session-queue   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/DeleteGameSessionQueue>`_


========
Synopsis
========

::

    delete-game-session-queue
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  Descriptive label that is associated with queue. Queue names must be unique within each region.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

