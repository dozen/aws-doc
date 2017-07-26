[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb describe-limits:


***************
describe-limits
***************



===========
Description
===========



Returns the current provisioned-capacity limits for your AWS account in a region, both for the region as a whole and for any one DynamoDB table that you create there.

 

When you establish an AWS account, the account has initial limits on the maximum read capacity units and write capacity units that you can provision across all of your DynamoDB tables in a given region. Also, there are per-table limits that apply when you create a table there. For more information, see `Limits <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Limits.html>`_ page in the *Amazon DynamoDB Developer Guide* .

 

Although you can increase these limits by filing a case at `AWS Support Center <https://console.aws.amazon.com/support/home#/>`_ , obtaining the increase is not instantaneous. The ``describe-limits`` action lets you write code to compare the capacity you are currently using to those limits imposed by your account so that you have enough time to apply for an increase before you hit a limit.

 

For example, you could use one of the AWS SDKs to do the following:

 

 
* Call ``describe-limits`` for a particular region to obtain your current account limits on provisioned capacity there. 
 
* Create a variable to hold the aggregate read capacity units provisioned for all your tables in that region, and one to hold the aggregate write capacity units. Zero them both. 
 
* Call ``list-tables`` to obtain a list of all your DynamoDB tables. 
 
* For each table name listed by ``list-tables`` , do the following: 

   
  * Call ``describe-table`` with the table name. 
   
  * Use the data returned by ``describe-table`` to add the read capacity units and write capacity units provisioned for the table itself to your variables. 
   
  * If the table has one or more global secondary indexes (GSIs), loop over these GSIs and add their provisioned capacity values to your variables as well. 
   

 
 
* Report the account limits for that region returned by ``describe-limits`` , along with the total current provisioned capacity levels you have calculated. 
 

 

This will let you see whether you are getting close to your account-level limits.

 

The per-table limits apply only when you are creating a new table. They restrict the sum of the provisioned capacity of the new table itself and all its global secondary indexes.

 

For existing tables and their GSIs, DynamoDB will not let you increase provisioned capacity extremely rapidly, but the only upper limit that applies is that the aggregate provisioned capacity over all your tables and GSIs cannot exceed either of the per-account limits.

 

.. note::

   

   ``describe-limits`` should only be called periodically. You can expect throttling errors if you call it more than once in a minute.

   

 

The ``describe-limits`` Request element has no content.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dynamodb-2012-08-10/DescribeLimits>`_


========
Synopsis
========

::

    describe-limits
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

AccountMaxReadCapacityUnits -> (long)

  

  The maximum total read capacity units that your account allows you to provision across all of your tables in this region.

  

  

AccountMaxWriteCapacityUnits -> (long)

  

  The maximum total write capacity units that your account allows you to provision across all of your tables in this region.

  

  

TableMaxReadCapacityUnits -> (long)

  

  The maximum read capacity units that your account allows you to provision for a new table that you are creating in this region, including the read capacity units provisioned for its global secondary indexes (GSIs).

  

  

TableMaxWriteCapacityUnits -> (long)

  

  The maximum write capacity units that your account allows you to provision for a new table that you are creating in this region, including the write capacity units provisioned for its global secondary indexes (GSIs).

  

  

