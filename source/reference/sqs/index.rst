[ :ref:`aws <cli:aws>` ]

.. _cli:aws sqs:


***
sqs
***



===========
Description
===========



Welcome to the *Amazon Simple Queue Service API Reference* . This section describes who should read this guide, how the guide is organized, and other resources related to the Amazon Simple Queue Service (Amazon SQS).

 

Amazon SQS offers reliable and scalable hosted queues for storing messages as they travel between computers. By using Amazon SQS, you can move data between distributed components of your applications that perform different tasks without losing messages or requiring each component to be always available.

 

Helpful Links: 

 
* `Current WSDL (2012-11-05)`_ 
 
* `Making API Requests`_ 
 
* `Amazon SQS product page`_ 
 
* `Using Amazon SQS Message Attributes`_ 
 
* `Using Amazon SQS Dead Letter Queues`_ 
 
* `Regions and Endpoints`_ 
 

 

 

We also provide SDKs that enable you to access Amazon SQS from your preferred programming language. The SDKs contain functionality that automatically takes care of tasks such as:

 

 

 
* Cryptographically signing your service requests
 
* Retrying requests
 
* Handling error responses
 

 

 

For a list of available SDKs, go to `Tools for Amazon Web Services`_ .



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  add-permission
  change-message-visibility
  change-message-visibility-batch
  create-queue
  delete-message
  delete-message-batch
  delete-queue
  get-queue-attributes
  get-queue-url
  list-dead-letter-source-queues
  list-queues
  purge-queue
  receive-message
  remove-permission
  send-message
  send-message-batch
  set-queue-attributes


.. _Current WSDL (2012-11-05): http://queue.amazonaws.com/doc/2012-11-05/QueueService.wsdl
.. _Regions and Endpoints: http://docs.aws.amazon.com/general/latest/gr/rande.html#sqs_region
.. _Amazon SQS product page: http://aws.amazon.com/sqs/
.. _Tools for Amazon Web Services: http://aws.amazon.com/tools/
.. _Making API Requests: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/MakingRequestsArticle.html
.. _Using Amazon SQS Message Attributes: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/SQSMessageAttributes.html
.. _Using Amazon SQS Dead Letter Queues: http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/SQSDeadLetterQueue.html
