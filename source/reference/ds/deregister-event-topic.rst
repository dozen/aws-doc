[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds deregister-event-topic:


**********************
deregister-event-topic
**********************



===========
Description
===========



Removes the specified directory as a publisher to the specified SNS topic.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/DeregisterEventTopic>`_


========
Synopsis
========

::

    deregister-event-topic
  --directory-id <value>
  --topic-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-id`` (string)


  The Directory ID to remove as a publisher. This directory will no longer send messages to the specified SNS topic.

  

``--topic-name`` (string)


  The name of the SNS topic from which to remove the directory as a publisher.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

