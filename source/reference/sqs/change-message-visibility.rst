[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs change-message-visibility:


*************************
change-message-visibility
*************************



===========
Description
===========



Changes the visibility timeout of a specified message in a queue to a new value. The maximum allowed timeout value you can set the value to is 12 hours. This means you can't extend the timeout of a message in an existing queue to more than a total visibility timeout of 12 hours. (For more information visibility timeout, see `Visibility Timeout`_ in the *Amazon SQS Developer Guide* .)

 

For example, let's say you have a message and its default message visibility timeout is 5 minutes. After 3 minutes, you call ``ChangeMessageVisiblity`` with a timeout of 10 minutes. At that time, the timeout for the message would be extended by 10 minutes beyond the time of the change-message-visibility call. This results in a total visibility timeout of 13 minutes. You can continue to call change-message-visibility to extend the visibility timeout to a maximum of 12 hours. If you try to extend beyond 12 hours, the request will be rejected.

 

.. note::

  

  There is a 120,000 limit for the number of inflight messages per queue. Messages are inflight after they have been received from the queue by a consuming component, but have not yet been deleted from the queue. If you reach the 120,000 limit, you will receive an OverLimit error message from Amazon SQS. To help avoid reaching the limit, you should delete the messages from the queue after they have been processed. You can also increase the number of queues you use to process the messages. 

  

 

.. warning::

  If you attempt to set the ``VisibilityTimeout`` to an amount more than the maximum time left, Amazon SQS returns an error. It will not automatically recalculate and increase the timeout to the maximum time remaining.

 

.. warning::

  Unlike with a queue, when you change the visibility timeout for a specific message, that timeout value is applied immediately but is not saved in memory for that message. If you don't delete a message after it is received, the visibility timeout for the message the next time it is received reverts to the original timeout value, not the value you set with the ``change-message-visibility`` action.



========
Synopsis
========

::

    change-message-visibility
  --queue-url <value>
  --receipt-handle <value>
  --visibility-timeout <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue to take action on.

  

``--receipt-handle`` (string)


  The receipt handle associated with the message whose visibility timeout should be changed. This parameter is returned by the  receive-message action.

  

``--visibility-timeout`` (integer)


  The new value (in seconds - from 0 to 43200 - maximum 12 hours) for the message's visibility timeout.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

.. _Visibility Timeout: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/AboutVT.html
