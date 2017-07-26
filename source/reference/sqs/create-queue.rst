[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs create-queue:


************
create-queue
************



===========
Description
===========



Creates a new queue, or returns the URL of an existing one. When you request ``create-queue`` , you provide a name for the queue. To successfully create a new queue, you must provide a name that is unique within the scope of your own queues.

 

.. note::

   

  If you delete a queue, you must wait at least 60 seconds before creating a queue with the same name.

   

 

You may pass one or more attributes in the request. If you do not provide a value for any attribute, the queue will have the default value for that attribute. Permitted attributes are the same that can be set using  set-queue-attributes .

 

.. note::

  

  Use  get-queue-url to get a queue's URL.  get-queue-url requires only the ``QueueName`` parameter.

  

 

If you provide the name of an existing queue, along with the exact names and values of all the queue's attributes, ``create-queue`` returns the queue URL for the existing queue. If the queue name, attribute names, or attribute values do not match an existing queue, ``create-queue`` returns an error.

 

.. note::

  Some API actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this: 

 

``Attribute.1=this`` 

 

``Attribute.2=that`` 



========
Synopsis
========

::

    create-queue
  --queue-name <value>
  [--attributes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--queue-name`` (string)


  The name for the queue to be created.

  

``--attributes`` (map)


  A map of attributes with their corresponding values.

   

  The following lists the names, descriptions, and values of the special request parameters the ``create-queue`` action uses:

   

   

   
  * ``DelaySeconds`` - The time in seconds that the delivery of all messages in the queue will be delayed. An integer from 0 to 900 (15 minutes). The default for this attribute is 0 (zero).
   
  * ``MaximumMessageSize`` - The limit of how many bytes a message can contain before Amazon SQS rejects it. An integer from 1024 bytes (1 KiB) up to 262144 bytes (256 KiB). The default for this attribute is 262144 (256 KiB).
   
  * ``MessageRetentionPeriod`` - The number of seconds Amazon SQS retains a message. Integer representing seconds, from 60 (1 minute) to 1209600 (14 days). The default for this attribute is 345600 (4 days).
   
  * ``Policy`` - The queue's policy. A valid AWS policy. For more information about policy structure, see `Overview of AWS IAM Policies`_ in the *Amazon IAM User Guide* .
   
  * ``ReceiveMessageWaitTimeSeconds`` - The time for which a  receive-message call will wait for a message to arrive. An integer from 0 to 20 (seconds). The default for this attribute is 0. 
   
  * ``VisibilityTimeout`` - The visibility timeout for the queue. An integer from 0 to 43200 (12 hours). The default for this attribute is 30. For more information about visibility timeout, see `Visibility Timeout`_ in the *Amazon SQS Developer Guide* .
   

   

  



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

  

  The URL for the created Amazon SQS queue.

  

  



.. _Overview of AWS IAM Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/PoliciesOverview.html
.. _Visibility Timeout: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/AboutVT.html
