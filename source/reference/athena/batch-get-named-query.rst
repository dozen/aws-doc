[ :ref:`aws <cli:aws>` . :ref:`athena <cli:aws athena>` ]

.. _cli:aws athena batch-get-named-query:


*********************
batch-get-named-query
*********************



===========
Description
===========



Returns the details of a single named query or a list of up to 50 queries, which you provide as an array of query ID strings. Use  list-named-queries to get the list of named query IDs. If information could not be retrieved for a submitted query ID, information about the query ID submitted is listed under  UnprocessedNamedQueryId . Named queries are different from executed queries. Use  batch-get-query-execution to get details about each unique query execution, and  list-query-executions to get a list of query execution IDs.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/athena-2017-05-18/BatchGetNamedQuery>`_


========
Synopsis
========

::

    batch-get-named-query
  --named-query-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--named-query-ids`` (list)


  An array of query IDs.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NamedQueries -> (list)

  

  Information about the named query IDs submitted.

  

  (structure)

    

    A query, where ``QueryString`` is the SQL query statements that comprise the query.

    

    Name -> (string)

      

      The plain-language name of the query.

      

      

    Description -> (string)

      

      A brief description of the query.

      

      

    Database -> (string)

      

      The database to which the query belongs.

      

      

    QueryString -> (string)

      

      The SQL query statements that comprise the query.

      

      

    NamedQueryId -> (string)

      

      The unique identifier of the query.

      

      

    

  

UnprocessedNamedQueryIds -> (list)

  

  Information about provided query IDs.

  

  (structure)

    

    Information about a named query ID that could not be processed.

    

    NamedQueryId -> (string)

      

      The unique identifier of the named query.

      

      

    ErrorCode -> (string)

      

      The error code returned when the processing request for the named query failed, if applicable.

      

      

    ErrorMessage -> (string)

      

      The error message returned when the processing request for the named query failed, if applicable.

      

      

    

  

