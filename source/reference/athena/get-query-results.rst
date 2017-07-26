[ :ref:`aws <cli:aws>` . :ref:`athena <cli:aws athena>` ]

.. _cli:aws athena get-query-results:


*****************
get-query-results
*****************



===========
Description
===========



Returns the results of a single query execution specified by ``query-execution-id`` . This request does not execute the query but returns results. Use  start-query-execution to run a query.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/athena-2017-05-18/GetQueryResults>`_


``get-query-results`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ResultSet``


========
Synopsis
========

::

    get-query-results
  --query-execution-id <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--query-execution-id`` (string)


  The unique ID of the query execution.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ResultSet -> (structure)

  

  The results of the query execution.

  

  Rows -> (list)

    

    The rows in the table.

    

    (structure)

      

      The rows that comprise a query result table.

      

      Data -> (list)

        

        The data that populates a row in a query result table.

        

        (structure)

          

          A piece of data (a field in the table).

          

          VarCharValue -> (string)

            

            The value of the datum.

            

            

          

        

      

    

  ResultSetMetadata -> (structure)

    

    The metadata that describes the column structure and data types of a table of query results.

    

    ColumnInfo -> (list)

      

      Information about the columns in a query execution result.

      

      (structure)

        

        Information about the columns in a query execution result.

        

        CatalogName -> (string)

          

          The catalog to which the query results belong.

          

          

        SchemaName -> (string)

          

          The schema name (database name) to which the query results belong.

          

          

        TableName -> (string)

          

          The table name for the query results.

          

          

        Name -> (string)

          

          The name of the column.

          

          

        Label -> (string)

          

          A column label.

          

          

        Type -> (string)

          

          The data type of the column.

          

          

        Precision -> (integer)

          

          For ``DECIMAL`` data types, specifies the total number of digits, up to 38. For performance reasons, we recommend up to 18 digits.

          

          

        Scale -> (integer)

          

          For ``DECIMAL`` data types, specifies the total number of digits in the fractional part of the value. Defaults to 0.

          

          

        Nullable -> (string)

          

          Indicates the column's nullable status.

          

          

        CaseSensitive -> (boolean)

          

          Indicates whether values in the column are case-sensitive.

          

          

        

      

    

  

NextToken -> (string)

  

  A token to be used by the next request if this request is truncated.

  

  

