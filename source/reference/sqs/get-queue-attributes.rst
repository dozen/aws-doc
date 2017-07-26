[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs get-queue-attributes:


********************
get-queue-attributes
********************



===========
Description
===========



Gets attributes for the specified queue.

 

.. note::

   

  To determine whether a queue is `FIFO <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues.html>`_ , you can check whether ``QueueName`` ends with the ``.fifo`` suffix.

   

 

.. note::

   

  Some actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this:

   

   ``Attribute.1=this``  

   

   ``Attribute.2=that``  

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sqs-2012-11-05/GetQueueAttributes>`_


========
Synopsis
========

::

    get-queue-attributes
  --queue-url <value>
  [--attribute-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue whose attribute information is retrieved.

   

  Queue URLs are case-sensitive.

  

``--attribute-names`` (list)


  A list of attributes for which to retrieve information.

   

  .. note::

     

    In the future, new attributes might be added. If you write code that calls this action, we recommend that you structure your code so that it can handle new attributes gracefully.

     

   

  The following attributes are supported:

   

   
  * ``All`` - Returns all values.  
   
  * ``ApproximateNumberOfMessages`` - Returns the approximate number of visible messages in a queue. For more information, see `Resources Required to Process Messages <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-resources-required-process-messages.html>`_ in the *Amazon SQS Developer Guide* .  
   
  * ``ApproximateNumberOfMessagesDelayed`` - Returns the approximate number of messages that are waiting to be added to the queue.  
   
  * ``ApproximateNumberOfMessagesNotVisible`` - Returns the approximate number of messages that have not timed-out and aren't deleted. For more information, see `Resources Required to Process Messages <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-resources-required-process-messages.html>`_ in the *Amazon SQS Developer Guide* .  
   
  * ``CreatedTimestamp`` - Returns the time when the queue was created in seconds (`epoch time <http://en.wikipedia.org/wiki/Unix_time>`_ ). 
   
  * ``DelaySeconds`` - Returns the default delay on the queue in seconds. 
   
  * ``LastModifiedTimestamp`` - Returns the time when the queue was last changed in seconds (`epoch time <http://en.wikipedia.org/wiki/Unix_time>`_ ). 
   
  * ``MaximumMessageSize`` - Returns the limit of how many bytes a message can contain before Amazon SQS rejects it. 
   
  * ``MessageRetentionPeriod`` - Returns the length of time, in seconds, for which Amazon SQS retains a message. 
   
  * ``Policy`` - Returns the policy of the queue. 
   
  * ``QueueArn`` - Returns the Amazon resource name (ARN) of the queue. 
   
  * ``ReceiveMessageWaitTimeSeconds`` - Returns the length of time, in seconds, for which the ``receive-message`` action waits for a message to arrive.  
   
  * ``RedrivePolicy`` - Returns the parameters for dead letter queue functionality of the source queue. For more information about the redrive policy and dead letter queues, see `Using Amazon SQS Dead Letter Queues <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-dead-letter-queues.html>`_ in the *Amazon SQS Developer Guide* .  
   
  * ``VisibilityTimeout`` - Returns the visibility timeout for the queue. For more information about the visibility timeout, see `Visibility Timeout <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html>`_ in the *Amazon SQS Developer Guide* .  
   

   

  The following attributes apply only to `server-side-encryption <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-server-side-encryption.html>`_ :

   

   
  * ``KmsMasterKeyId`` - Returns the ID of an AWS-managed customer master key (CMK) for Amazon SQS or a custom CMK. For more information, see `Key Terms <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-server-side-encryption.html#sqs-sse-key-terms>`_ .  
   
  * ``KmsDataKeyReusePeriodSeconds`` - Returns the length of time, in seconds, for which Amazon SQS can reuse a data key to encrypt or decrypt messages before calling AWS KMS again.  
   

   

  The following attributes apply only to `FIFO (first-in-first-out) queues <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues.html>`_ :

   

   
  * ``FifoQueue`` - Returns whether the queue is FIFO. For more information, see `FIFO Queue Logic <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues.html#FIFO-queues-understanding-logic>`_ in the *Amazon SQS Developer Guide* . 

  .. note::

     To determine whether a queue is `FIFO <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues.html>`_ , you can check whether ``QueueName`` ends with the ``.fifo`` suffix. 

   
   
  * ``ContentBasedDeduplication`` - Returns whether content-based deduplication is enabled for the queue. For more information, see `Exactly-Once Processing <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues.html#FIFO-queues-exactly-once-processing>`_ in the *Amazon SQS Developer Guide* .  
   

  



Syntax::

  "string" "string" ...

  Where valid values are:
    All
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
    FifoQueue
    ContentBasedDeduplication
    KmsMasterKeyId
    KmsDataKeyReusePeriodSeconds





``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  A map of attributes to their respective values.

  

  Name -> (string)

    

    

  Value -> (string)

    

    

  

