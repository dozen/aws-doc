[ :ref:`aws <cli:aws>` ]

.. _cli:aws sqs:


***
sqs
***



===========
Description
===========



Welcome to the *Amazon Simple Queue Service API Reference* .

 

Amazon Simple Queue Service (Amazon SQS) is a reliable, highly-scalable hosted queue for storing messages as they travel between applications or microservices. Amazon SQS moves data between distributed application components and helps you decouple these components.

 

.. note::

   

   `Standard queues <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/standard-queues.html>`_ are available in all regions. `FIFO queues <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues.html>`_ are available in US West (Oregon) and US East (Ohio).

   

 

You can use `AWS SDKs <http://aws.amazon.com/tools/#sdk>`_ to access Amazon SQS using your favorite programming language. The SDKs perform tasks such as the following automatically:

 

 
* Cryptographically sign your service requests 
 
* Retry requests 
 
* Handle error responses 
 

 

 **Additional Information**  

 

 
* `Amazon SQS Product Page <http://aws.amazon.com/sqs/>`_   
 
* *Amazon SQS Developer Guide*   

   
  * `Making API Requests <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/MakingRequestsArticle.html>`_   
   
  * `Using Amazon SQS Message Attributes <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-message-attributes.html>`_   
   
  * `Using Amazon SQS Dead Letter Queues <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-dead-letter-queues.html>`_   
   

 
 
* *Amazon Web Services General Reference*   

   
  * `Regions and Endpoints <http://docs.aws.amazon.com/general/latest/gr/rande.html#sqs_region>`_   
   

 
 



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
