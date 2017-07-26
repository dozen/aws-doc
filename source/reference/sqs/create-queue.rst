[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs create-queue:


************
create-queue
************



===========
Description
===========



Creates a new standard or FIFO queue. You can pass one or more attributes in the request. Keep the following caveats in mind:

 

 
* If you don't specify the ``FifoQueue`` attribute, Amazon SQS creates a standard queue. 

.. note::

   You can't change the queue type after you create it and you can't convert an existing standard queue into a FIFO queue. You must either create a new FIFO queue for your application or delete your existing standard queue and recreate it as a FIFO queue. For more information, see `Moving From a Standard Queue to a FIFO Queue <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues.html#FIFO-queues-moving>`_ in the *Amazon SQS Developer Guide* .  

 
 
* If you don't provide a value for an attribute, the queue is created with the default value for the attribute. 
 
* If you delete a queue, you must wait at least 60 seconds before creating a queue with the same name. 
 

 

To successfully create a new queue, you must provide a queue name that adheres to the `limits related to queues <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/limits-queues.html>`_ and is unique within the scope of your queues.

 

To get the queue URL, use the ``  get-queue-url `` action. ``  get-queue-url `` requires only the ``QueueName`` parameter. be aware of existing queue names:

 

 
* If you provide the name of an existing queue along with the exact names and values of all the queue's attributes, ``create-queue`` returns the queue URL for the existing queue. 
 
* If the queue name, attribute names, or attribute values don't match an existing queue, ``create-queue`` returns an error. 
 

 

.. note::

   

  Some actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this:

   

   ``Attribute.1=this``  

   

   ``Attribute.2=that``  

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sqs-2012-11-05/CreateQueue>`_


========
Synopsis
========

::

    create-queue
  --queue-name <value>
  [--attributes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--queue-name`` (string)


  The name of the new queue. The following limits apply to this name:

   

   
  * A queue name can have up to 80 characters. 
   
  * Valid values: alphanumeric characters, hyphens (``-`` ), and underscores (``_`` ). 
   
  * A FIFO queue name must end with the ``.fifo`` suffix. 
   

   

  Queue names are case-sensitive.

  

``--attributes`` (map)


  A map of attributes with their corresponding values.

   

  The following lists the names, descriptions, and values of the special request parameters that the ``create-queue`` action uses:

   

   
  * ``DelaySeconds`` - The length of time, in seconds, for which the delivery of all messages in the queue is delayed. Valid values: An integer from 0 to 900 seconds (15 minutes). The default is 0 (zero).  
   
  * ``MaximumMessageSize`` - The limit of how many bytes a message can contain before Amazon SQS rejects it. Valid values: An integer from 1,024 bytes (1 KiB) to 262,144 bytes (256 KiB). The default is 262,144 (256 KiB).  
   
  * ``MessageRetentionPeriod`` - The length of time, in seconds, for which Amazon SQS retains a message. Valid values: An integer from 60 seconds (1 minute) to 1,209,600 seconds (14 days). The default is 345,600 (4 days).  
   
  * ``Policy`` - The queue's policy. A valid AWS policy. For more information about policy structure, see `Overview of AWS IAM Policies <http://docs.aws.amazon.com/IAM/latest/UserGuide/PoliciesOverview.html>`_ in the *Amazon IAM User Guide* .  
   
  * ``ReceiveMessageWaitTimeSeconds`` - The length of time, in seconds, for which a ``  receive-message `` action waits for a message to arrive. Valid values: An integer from 0 to 20 (seconds). The default is 0 (zero).  
   
  * ``RedrivePolicy`` - The parameters for the dead letter queue functionality of the source queue. For more information about the redrive policy and dead letter queues, see `Using Amazon SQS Dead Letter Queues <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-dead-letter-queues.html>`_ in the *Amazon SQS Developer Guide* .  

  .. note::

     The dead letter queue of a FIFO queue must also be a FIFO queue. Similarly, the dead letter queue of a standard queue must also be a standard queue. 

   
   
  * ``VisibilityTimeout`` - The visibility timeout for the queue. Valid values: An integer from 0 to 43,200 (12 hours). The default is 30. For more information about the visibility timeout, see `Visibility Timeout <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html>`_ in the *Amazon SQS Developer Guide* . 
   

   

  The following attributes apply only to `server-side-encryption <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-server-side-encryption.html>`_ :

   

   
  * ``KmsMasterKeyId`` - The ID of an AWS-managed customer master key (CMK) for Amazon SQS or a custom CMK. For more information, see `Key Terms <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-server-side-encryption.html#sqs-sse-key-terms>`_ . While the alias of the AWS-managed CMK for Amazon SQS is always ``alias/aws/sqs`` , the alias of a custom CMK can, for example, be ``alias/aws/sqs`` . For more examples, see `KeyId <http://docs.aws.amazon.com/kms/latest/APIReference/API_DescribeKey.html#API_DescribeKey_RequestParameters>`_ in the *AWS Key Management Service API Reference* .  
   
  * ``KmsDataKeyReusePeriodSeconds`` - The length of time, in seconds, for which Amazon SQS can reuse a `data key <http://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#data-keys>`_ to encrypt or decrypt messages before calling AWS KMS again. An integer representing seconds, between 60 seconds (1 minute) and 86,400 seconds (24 hours). The default is 300 (5 minutes). A shorter time period provides better security but results in more calls to KMS which incur charges after Free Tier. For more information, see `How Does the Data Key Reuse Period Work? <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-server-side-encryption.html#sqs-how-does-the-data-key-reuse-period-work>`_ .  
   

   

  The following attributes apply only to `FIFO (first-in-first-out) queues <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues.html>`_ :

   

   
  * ``FifoQueue`` - Designates a queue as FIFO. Valid values: ``true`` , ``false`` . You can provide this attribute only during queue creation. You can't change it for an existing queue. When you set this attribute, you must also provide the ``MessageGroupId`` for your messages explicitly. For more information, see `FIFO Queue Logic <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues.html#FIFO-queues-understanding-logic>`_ in the *Amazon SQS Developer Guide* . 
   
  * ``ContentBasedDeduplication`` - Enables content-based deduplication. Valid values: ``true`` , ``false`` . For more information, see `Exactly-Once Processing <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues.html#FIFO-queues-exactly-once-processing>`_ in the *Amazon SQS Developer Guide* .  

     
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

**To create a queue**

This example creates a queue with the specified name, sets the message retention period to 3 days (3 days * 24 hours * 60 minutes * 60 seconds), and sets the queue's dead letter queue to the specified queue with a maximum receive count of 1,000 messages.

Command::

  aws sqs create-queue --queue-name MyQueue --attributes file://create-queue.json

Input file (create-queue.json)::

  {
    "RedrivePolicy": "{\"deadLetterTargetArn\":\"arn:aws:sqs:us-east-1:80398EXAMPLE:MyDeadLetterQueue\",\"maxReceiveCount\":\"1000\"}",
    "MessageRetentionPeriod": "259200"  
  }

Output::

  {
    "QueueUrl": "https://queue.amazonaws.com/80398EXAMPLE/MyQueue"
  }



======
Output
======

QueueUrl -> (string)

  

  The URL of the created Amazon SQS queue.

  

  

