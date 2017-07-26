[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs change-message-visibility:


*************************
change-message-visibility
*************************



===========
Description
===========



Changes the visibility timeout of a specified message in a queue to a new value. The maximum allowed timeout value is 12 hours. Thus, you can't extend the timeout of a message in an existing queue to more than a total visibility timeout of 12 hours. For more information, see `Visibility Timeout <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html>`_ in the *Amazon SQS Developer Guide* .

 

For example, you have a message and with the default visibility timeout of 5 minutes. After 3 minutes, you call ``ChangeMessageVisiblity`` with a timeout of 10 minutes. At that time, the timeout for the message is extended by 10 minutes beyond the time of the ``change-message-visibility`` action. This results in a total visibility timeout of 13 minutes. You can continue to call the ``change-message-visibility`` to extend the visibility timeout to a maximum of 12 hours. If you try to extend the visibility timeout beyond 12 hours, your request is rejected.

 

A message is considered to be *in flight* after it's received from a queue by a consumer, but not yet deleted from the queue.

 

For standard queues, there can be a maximum of 120,000 inflight messages per queue. If you reach this limit, Amazon SQS returns the ``OverLimit`` error message. To avoid reaching the limit, you should delete messages from the queue after they're processed. You can also increase the number of queues you use to process your messages.

 

For FIFO queues, there can be a maximum of 20,000 inflight messages per queue. If you reach this limit, Amazon SQS returns no error messages.

 

.. warning::

   

  If you attempt to set the ``VisibilityTimeout`` to a value greater than the maximum time left, Amazon SQS returns an error. Amazon SQS doesn't automatically recalculate and increase the timeout to the maximum remaining time.

   

  Unlike with a queue, when you change the visibility timeout for a specific message the timeout value is applied immediately but isn't saved in memory for that message. If you don't delete a message after it is received, the visibility timeout for the message reverts to the original timeout value (not to the value you set using the ``change-message-visibility`` action) the next time the message is received.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sqs-2012-11-05/ChangeMessageVisibility>`_


========
Synopsis
========

::

    change-message-visibility
  --queue-url <value>
  --receipt-handle <value>
  --visibility-timeout <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue whose message's visibility is changed.

   

  Queue URLs are case-sensitive.

  

``--receipt-handle`` (string)


  The receipt handle associated with the message whose visibility timeout is changed. This parameter is returned by the ``  receive-message `` action.

  

``--visibility-timeout`` (integer)


  The new value for the message's visibility timeout (in seconds). Values values: ``0`` to ``43200`` . Maximum: 12 hours.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To change a message's timeout visibility**

This example changes the specified message's timeout visibility to 10 hours (10 hours * 60 minutes * 60 seconds).

Command::

  aws sqs change-message-visibility --queue-url https://sqs.us-east-1.amazonaws.com/80398EXAMPLE/MyQueue --receipt-handle AQEBTpyI...t6HyQg== --visibility-timeout 36000

Output::

  None.

======
Output
======

None