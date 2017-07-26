[ :ref:`aws <cli:aws>` ]

.. _cli:aws dynamodbstreams:


***************
dynamodbstreams
***************



===========
Description
===========

 

This is the Amazon DynamoDB Streams API Reference. This guide describes the low-level API actions for accessing streams and processing stream records. For information about application development with DynamoDB Streams, see the `Amazon DynamoDB Developer Guide`_ .

 

Note that this document is intended for use with the following DynamoDB documentation:

 

 
* `Amazon DynamoDB Developer Guide`_   
 
* `Amazon DynamoDB API Reference`_   
 

 

The following are short descriptions of each low-level DynamoDB Streams API action, organized by function.

 

 
* *describe-stream* - Returns detailed information about a particular stream.
 
* *get-records* - Retrieves the stream records from within a shard. 
 
* *get-shard-iterator* - Returns information on how to retrieve the streams record from a shard with a given shard ID. 
 
* *list-streams* - Returns a list of all the streams associated with the current AWS account and endpoint. 
 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  describe-stream
  get-records
  get-shard-iterator
  list-streams


.. _Amazon DynamoDB Developer Guide: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/
.. _Amazon DynamoDB API Reference: http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/
