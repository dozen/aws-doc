[ :ref:`aws <cli:aws>` . :ref:`athena <cli:aws athena>` ]

.. _cli:aws athena get-query-execution:


*******************
get-query-execution
*******************



===========
Description
===========



Returns information about a single execution of a query. Each time a query executes, information about the query execution is saved with a unique ID.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/athena-2017-05-18/GetQueryExecution>`_


========
Synopsis
========

::

    get-query-execution
  --query-execution-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--query-execution-id`` (string)


  The unique ID of the query execution.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

QueryExecution -> (structure)

  

  Information about the query execution.

  

  QueryExecutionId -> (string)

    

    The unique identifier for each query execution.

    

    

  Query -> (string)

    

    The SQL query statements which the query execution ran.

    

    

  ResultConfiguration -> (structure)

    

    The location in Amazon S3 where query results were stored and the encryption option, if any, used for query results.

    

    OutputLocation -> (string)

      

      The location in S3 where query results are stored.

      

      

    EncryptionConfiguration -> (structure)

      

      If query results are encrypted in S3, indicates the S3 encryption option used (for example, ``SSE-KMS`` or ``CSE-KMS`` and key information.

      

      EncryptionOption -> (string)

        

        Indicates whether Amazon S3 server-side encryption with Amazon S3-managed keys (``SSE-S3`` ), server-side encryption with KMS-managed keys (``SSE-KMS`` ), or client-side encryption with KMS-managed keys (CSE-KMS) is used.

        

        

      KmsKey -> (string)

        

        For ``SSE-KMS`` and ``CSE-KMS`` , this is the KMS key ARN or ID.

        

        

      

    

  QueryExecutionContext -> (structure)

    

    The database in which the query execution occurred.

    

    Database -> (string)

      

      The name of the database.

      

      

    

  Status -> (structure)

    

    The completion date, current state, submission time, and state change reason (if applicable) for the query execution.

    

    State -> (string)

      

      The state of query execution. ``SUBMITTED`` indicates that the query is queued for execution. ``RUNNING`` indicates that the query is scanning data and returning results. ``SUCCEEDED`` indicates that the query completed without error. ``FAILED`` indicates that the query experienced an error and did not complete processing. ``CANCELLED`` indicates that user input interrupted query execution.

      

      

    StateChangeReason -> (string)

      

      Further detail about the status of the query.

      

      

    SubmissionDateTime -> (timestamp)

      

      The date and time that the query was submitted.

      

      

    CompletionDateTime -> (timestamp)

      

      The date and time that the query completed.

      

      

    

  Statistics -> (structure)

    

    The amount of data scanned during the query execution and the amount of time that it took to execute.

    

    EngineExecutionTimeInMillis -> (long)

      

      The number of milliseconds that the query took to execute.

      

      

    DataScannedInBytes -> (long)

      

      The number of bytes in the data that was queried.

      

      

    

  

