[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs set-queue-attributes:


********************
set-queue-attributes
********************



===========
Description
===========



Sets the value of one or more queue attributes. When you change a queue's attributes, the change can take up to 60 seconds for most of the attributes to propagate throughout the SQS system. Changes made to the ``MessageRetentionPeriod`` attribute can take up to 15 minutes.

 

.. note::

  Going forward, new attributes might be added. If you are writing code that calls this action, we recommend that you structure your code so that it can handle new attributes gracefully.



========
Synopsis
========

::

    set-queue-attributes
  --queue-url <value>
  --attributes <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue to take action on.

  

``--attributes`` (map)


  A map of attributes to set.

   

  The following lists the names, descriptions, and values of the special request parameters the ``set-queue-attributes`` action uses:

   

   

   
  * ``DelaySeconds`` - The time in seconds that the delivery of all messages in the queue will be delayed. An integer from 0 to 900 (15 minutes). The default for this attribute is 0 (zero).
   
  * ``MaximumMessageSize`` - The limit of how many bytes a message can contain before Amazon SQS rejects it. An integer from 1024 bytes (1 KiB) up to 262144 bytes (256 KiB). The default for this attribute is 262144 (256 KiB).
   
  * ``MessageRetentionPeriod`` - The number of seconds Amazon SQS retains a message. Integer representing seconds, from 60 (1 minute) to 1209600 (14 days). The default for this attribute is 345600 (4 days).
   
  * ``Policy`` - The queue's policy. A valid AWS policy. For more information about policy structure, see `Overview of AWS IAM Policies`_ in the *Amazon IAM User Guide* .
   
  * ``ReceiveMessageWaitTimeSeconds`` - The time for which a receive-message call will wait for a message to arrive. An integer from 0 to 20 (seconds). The default for this attribute is 0. 
   
  * ``VisibilityTimeout`` - The visibility timeout for the queue. An integer from 0 to 43200 (12 hours). The default for this attribute is 30. For more information about visibility timeout, see Visibility Timeout in the *Amazon SQS Developer Guide* .
   
  * ``RedrivePolicy`` - The parameters for dead letter queue functionality of the source queue. For more information about RedrivePolicy and dead letter queues, see Using Amazon SQS Dead Letter Queues in the *Amazon SQS Developer Guide* .
   

   

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string
  
  Where valid key names are:
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




JSON Syntax::

  {"Policy"|"VisibilityTimeout"|"MaximumMessageSize"|"MessageRetentionPeriod"|"ApproximateNumberOfMessages"|"ApproximateNumberOfMessagesNotVisible"|"CreatedTimestamp"|"LastModifiedTimestamp"|"QueueArn"|"ApproximateNumberOfMessagesDelayed"|"DelaySeconds"|"ReceiveMessageWaitTimeSeconds"|"RedrivePolicy": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

.. _Overview of AWS IAM Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/PoliciesOverview.html
