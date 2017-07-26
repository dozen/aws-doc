[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs set-queue-attributes:


********************
set-queue-attributes
********************



===========
Description
===========



Sets the value of one or more queue attributes. When you change a queue's attributes, the change can take up to 60 seconds for most of the attributes to propagate throughout the Amazon SQS system. Changes made to the ``MessageRetentionPeriod`` attribute can take up to 15 minutes.

 

.. note::

   

  In the future, new attributes might be added. If you write code that calls this action, we recommend that you structure your code so that it can handle new attributes gracefully.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sqs-2012-11-05/SetQueueAttributes>`_


========
Synopsis
========

::

    set-queue-attributes
  --queue-url <value>
  --attributes <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue whose attributes are set.

   

  Queue URLs are case-sensitive.

  

``--attributes`` (map)


  A map of attributes to set.

   

  The following lists the names, descriptions, and values of the special request parameters that the ``set-queue-attributes`` action uses:

   

   
  * ``DelaySeconds`` - The length of time, in seconds, for which the delivery of all messages in the queue is delayed. Valid values: An integer from 0 to 900 (15 minutes). The default is 0 (zero).  
   
  * ``MaximumMessageSize`` - The limit of how many bytes a message can contain before Amazon SQS rejects it. Valid values: An integer from 1,024 bytes (1 KiB) up to 262,144 bytes (256 KiB). The default is 262,144 (256 KiB).  
   
  * ``MessageRetentionPeriod`` - The length of time, in seconds, for which Amazon SQS retains a message. Valid values: An integer representing seconds, from 60 (1 minute) to 1,209,600 (14 days). The default is 345,600 (4 days).  
   
  * ``Policy`` - The queue's policy. A valid AWS policy. For more information about policy structure, see `Overview of AWS IAM Policies <http://docs.aws.amazon.com/IAM/latest/UserGuide/PoliciesOverview.html>`_ in the *Amazon IAM User Guide* .  
   
  * ``ReceiveMessageWaitTimeSeconds`` - The length of time, in seconds, for which a ``  receive-message `` action waits for a message to arrive. Valid values: an integer from 0 to 20 (seconds). The default is 0.  
   
  * ``RedrivePolicy`` - The parameters for the dead letter queue functionality of the source queue. For more information about the redrive policy and dead letter queues, see `Using Amazon SQS Dead Letter Queues <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-dead-letter-queues.html>`_ in the *Amazon SQS Developer Guide* .  

  .. note::

     The dead letter queue of a FIFO queue must also be a FIFO queue. Similarly, the dead letter queue of a standard queue must also be a standard queue. 

   
   
  * ``VisibilityTimeout`` - The visibility timeout for the queue. Valid values: an integer from 0 to 43,200 (12 hours). The default is 30. For more information about the visibility timeout, see `Visibility Timeout <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html>`_ in the *Amazon SQS Developer Guide* . 
   

   

  The following attributes apply only to `server-side-encryption <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-server-side-encryption.html>`_ :

   

   
  * ``KmsMasterKeyId`` - The ID of an AWS-managed customer master key (CMK) for Amazon SQS or a custom CMK. For more information, see `Key Terms <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-server-side-encryption.html#sqs-sse-key-terms>`_ . While the alias of the AWS-managed CMK for Amazon SQS is always ``alias/aws/sqs`` , the alias of a custom CMK can, for example, be ``alias/aws/sqs`` . For more examples, see `KeyId <http://docs.aws.amazon.com/kms/latest/APIReference/API_DescribeKey.html#API_DescribeKey_RequestParameters>`_ in the *AWS Key Management Service API Reference* .  
   
  * ``KmsDataKeyReusePeriodSeconds`` - The length of time, in seconds, for which Amazon SQS can reuse a `data key <http://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#data-keys>`_ to encrypt or decrypt messages before calling AWS KMS again. An integer representing seconds, between 60 seconds (1 minute) and 86,400 seconds (24 hours). The default is 300 (5 minutes). A shorter time period provides better security but results in more calls to KMS which incur charges after Free Tier. For more information, see `How Does the Data Key Reuse Period Work? <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-server-side-encryption.html#sqs-how-does-the-data-key-reuse-period-work>`_ .  
   

   

  The following attribute applies only to `FIFO (first-in-first-out) queues <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues.html>`_ :

   

   
  * ``ContentBasedDeduplication`` - Enables content-based deduplication. For more information, see `Exactly-Once Processing <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues.html#FIFO-queues-exactly-once-processing>`_ in the *Amazon SQS Developer Guide* .  

     
    * Every message must have a unique ``MessageDeduplicationId`` , 

       
      * You may provide a ``MessageDeduplicationId`` explicitly. 
       
      * If you aren't able to provide a ``MessageDeduplicationId`` and you enable ``ContentBasedDeduplication`` for your queue, Amazon SQS uses a SHA-256 hash to generate the ``MessageDeduplicationId`` using the body of the message (but not the attributes of the message).  
       
      * If you don't provide a ``MessageDeduplicationId`` and the queue doesn't have ``ContentBasedDeduplication`` set, the action fails with an error. 
       
      * If the queue has ``ContentBasedDeduplication`` set, your ``MessageDeduplicationId`` overrides the generated one. 
       

     
     
    * When ``ContentBasedDeduplication`` is in effect, messages with identical content sent within the deduplication interval are treated as duplicates and only one copy of the message is delivered. 
     
    * If you send one message with ``ContentBasedDeduplication`` enabled and then another message with a ``MessageDeduplicationId`` that is the same as the one generated for the first ``MessageDeduplicationId`` , the two messages are treated as duplicates and only one copy of the message is delivered.  
     

   
   

   

  Any other valid special request parameters (such as the following) are ignored:

   

   
  * ``ApproximateNumberOfMessages``   
   
  * ``ApproximateNumberOfMessagesDelayed``   
   
  * ``ApproximateNumberOfMessagesNotVisible``   
   
  * ``CreatedTimestamp``   
   
  * ``LastModifiedTimestamp``   
   
  * ``QueueArn``   
   

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string
  
  Where valid key names are:
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




JSON Syntax::

  {"All"|"Policy"|"VisibilityTimeout"|"MaximumMessageSize"|"MessageRetentionPeriod"|"ApproximateNumberOfMessages"|"ApproximateNumberOfMessagesNotVisible"|"CreatedTimestamp"|"LastModifiedTimestamp"|"QueueArn"|"ApproximateNumberOfMessagesDelayed"|"DelaySeconds"|"ReceiveMessageWaitTimeSeconds"|"RedrivePolicy"|"FifoQueue"|"ContentBasedDeduplication"|"KmsMasterKeyId"|"KmsDataKeyReusePeriodSeconds": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To set queue attributes**

This example sets the specified queue to a delivery delay of 10 seconds, a maximum message size of 128 KB (128 KB * 1,024 bytes), a message retention period of 3 days (3 days * 24 hours * 60 minutes * 60 seconds), a receive message wait time of 20 seconds, and a default visibility timeout of 60 seconds. This example also associates the specified dead letter queue with a maximum receive count of 1,000 messages. 

Command::

  aws sqs set-queue-attributes --queue-url https://sqs.us-east-1.amazonaws.com/80398EXAMPLE/MyNewQueue --attributes file://set-queue-attributes.json
  
Input file (set-queue-attributes.json)::

  {
    "DelaySeconds": "10",
    "MaximumMessageSize": "131072",
    "MessageRetentionPeriod": "259200",
    "ReceiveMessageWaitTimeSeconds": "20",
    "RedrivePolicy": "{\"deadLetterTargetArn\":\"arn:aws:sqs:us-east-1:80398EXAMPLE:MyDeadLetterQueue\",\"maxReceiveCount\":\"1000\"}",
    "VisibilityTimeout": "60" 
  }

Output::

  None.


======
Output
======

None