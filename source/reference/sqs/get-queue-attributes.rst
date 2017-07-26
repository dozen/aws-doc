[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs get-queue-attributes:


********************
get-queue-attributes
********************



===========
Description
===========



Gets attributes for the specified queue. The following attributes are supported: 

 
* ``All`` - returns all values.
 
* ``ApproximateNumberOfMessages`` - returns the approximate number of visible messages in a queue. For more information, see `Resources Required to Process Messages`_ in the *Amazon SQS Developer Guide* .
 
* ``ApproximateNumberOfMessagesNotVisible`` - returns the approximate number of messages that are not timed-out and not deleted. For more information, see `Resources Required to Process Messages`_ in the *Amazon SQS Developer Guide* .
 
* ``VisibilityTimeout`` - returns the visibility timeout for the queue. For more information about visibility timeout, see `Visibility Timeout`_ in the *Amazon SQS Developer Guide* .
 
* ``CreatedTimestamp`` - returns the time when the queue was created (epoch time in seconds).
 
* ``LastModifiedTimestamp`` - returns the time when the queue was last changed (epoch time in seconds).
 
* ``Policy`` - returns the queue's policy.
 
* ``MaximumMessageSize`` - returns the limit of how many bytes a message can contain before Amazon SQS rejects it.
 
* ``MessageRetentionPeriod`` - returns the number of seconds Amazon SQS retains a message.
 
* ``QueueArn`` - returns the queue's Amazon resource name (ARN).
 
* ``ApproximateNumberOfMessagesDelayed`` - returns the approximate number of messages that are pending to be added to the queue.
 
* ``DelaySeconds`` - returns the default delay on the queue in seconds.
 
* ``ReceiveMessageWaitTimeSeconds`` - returns the time for which a receive-message call will wait for a message to arrive.
 
* ``RedrivePolicy`` - returns the parameters for dead letter queue functionality of the source queue. For more information about RedrivePolicy and dead letter queues, see `Using Amazon SQS Dead Letter Queues`_ in the *Amazon SQS Developer Guide* .
 

 

 

.. note::

  Going forward, new attributes might be added. If you are writing code that calls this action, we recommend that you structure your code so that it can handle new attributes gracefully.

 

.. note::

  Some API actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this: 

 

``Attribute.1=this`` 

 

``Attribute.2=that`` 



========
Synopsis
========

::

    get-queue-attributes
  --queue-url <value>
  [--attribute-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue to take action on.

  

``--attribute-names`` (list)


  A list of attributes to retrieve information for. 

  



Syntax::

  "string" "string" ...

  Where valid values are:
    Policy
    VisibilityTimeout
    MaximumMessageSize
    MessageRetentionPeriod
    ApproximateNumberOfMessages
    ApproximateNumberOfMessagesNotVisible
    CreatedTimestamp
    LastModifiedTimestamp
    QueueArn
    ApproximateNumberOfMessagesDelayed
    DelaySeconds
    ReceiveMessageWaitTimeSeconds
    RedrivePolicy





``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get a queue's attributes**

This example gets all of the specified queue's attributes.

Command::

  aws sqs get-queue-attributes --queue-url https://sqs.us-east-1.amazonaws.com/80398EXAMPLE/MyQueue --attribute-names All

Output::

  {
    "Attributes": {
      "ApproximateNumberOfMessagesNotVisible": "0",
      "RedrivePolicy": "{\"deadLetterTargetArn\":\"arn:aws:sqs:us-east-1:80398EXAMPLE:MyDeadLetterQueue\",\"maxReceiveCount\":1000}",
      "MessageRetentionPeriod": "345600",
      "ApproximateNumberOfMessagesDelayed": "0",
      "MaximumMessageSize": "262144",
      "CreatedTimestamp": "1442426968",
      "ApproximateNumberOfMessages": "0",
      "ReceiveMessageWaitTimeSeconds": "0",
      "DelaySeconds": "0",
      "VisibilityTimeout": "30",
      "LastModifiedTimestamp": "1442426968",
      "QueueArn": "arn:aws:sqs:us-east-1:80398EXAMPLE:MyNewQueue"
    }
  }

This example gets only the specified queue's maximum message size and visibility timeout attributes.

Command::

  aws sqs get-queue-attributes --queue-url https://sqs.us-east-1.amazonaws.com/80398EXAMPLE/MyNewQueue --attribute-names MaximumMessageSize VisibilityTimeout

Output::

  {
    "Attributes": {
      "VisibilityTimeout": "30",
      "MaximumMessageSize": "262144"
    }
  }


======
Output
======

Attributes -> (map)

  

  A map of attributes to the respective values.

  

  Name -> (string)

    

    The name of a queue attribute.

    

    

  Value -> (string)

    

    The value of a queue attribute.

    

    

  



.. _Using Amazon SQS Dead Letter Queues: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/SQSDeadLetterQueue.html
.. _Resources Required to Process Messages: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/ApproximateNumber.html
.. _Visibility Timeout: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/AboutVT.html
