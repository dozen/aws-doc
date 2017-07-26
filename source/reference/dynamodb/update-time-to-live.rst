[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb update-time-to-live:


*******************
update-time-to-live
*******************



===========
Description
===========



Specify the lifetime of individual table items. The database automatically removes the item at the expiration of the item. The update-time-to-live method will enable or disable TTL for the specified table. A successful ``update-time-to-live`` call returns the current ``time-to-live-specification`` ; it may take up to one hour for the change to fully process. 

 

TTL compares the current time in epoch time format to the time stored in the TTL attribute of an item. If the epoch time value stored in the attribute is less than the current time, the item is marked as expired and subsequently deleted.

 

.. note::

   

  The epoch time format is the number of seconds elapsed since 12:00:00 AM January 1st, 1970 UTC. 

   

 

DynamoDB deletes expired items on a best-effort basis to ensure availability of throughput for other data operations. 

 

.. warning::

   

  DynamoDB typically deletes expired items within two days of expiration. The exact duration within which an item gets deleted after expiration is specific to the nature of the workload. Items that have expired and not been deleted will still show up in reads, queries, and scans.

   

 

As items are deleted, they are removed from any Local Secondary Index and Global Secondary Index immediately in the same eventually consistent way as a standard delete operation.

 

For more information, see `Time To Live <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/TTL.html>`_ in the Amazon DynamoDB Developer Guide. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dynamodb-2012-08-10/UpdateTimeToLive>`_


========
Synopsis
========

::

    update-time-to-live
  --table-name <value>
  --time-to-live-specification <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--table-name`` (string)


  The name of the table to be configured.

  

``--time-to-live-specification`` (structure)


  Represents the settings used to enable or disable Time to Live for the specified table.

  



Shorthand Syntax::

    Enabled=boolean,AttributeName=string




JSON Syntax::

  {
    "Enabled": true|false,
    "AttributeName": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TimeToLiveSpecification -> (structure)

  

  Represents the output of an ``update-time-to-live`` operation.

  

  Enabled -> (boolean)

    

    Indicates whether Time To Live is to be enabled (true) or disabled (false) on the table.

    

    

  AttributeName -> (string)

    

    The name of the Time to Live attribute used to store the expiration time for items in the table.

    

    

  

