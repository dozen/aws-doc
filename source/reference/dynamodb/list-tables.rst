[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb list-tables:


***********
list-tables
***********



===========
Description
===========



Returns an array of table names associated with the current account and endpoint. The output from ``list-tables`` is paginated, with each page returning a maximum of 100 table names.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dynamodb-2012-08-10/ListTables>`_


``list-tables`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``TableNames``


========
Synopsis
========

::

    list-tables
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

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



========
Examples
========

**To list tables**

This example lists all of the tables associated with the current AWS account and endpoint

Command::

  aws dynamodb list-tables

Output::

  {
      "TableNames": [
          "Forum", 
          "ProductCatalog", 
          "Reply", 
          "Thread", 
      ]
  }


======
Output
======

TableNames -> (list)

  

  The names of the tables associated with the current account at the current endpoint. The maximum size of this array is 100.

   

  If ``LastEvaluatedTableName`` also appears in the output, you can use this value as the ``ExclusiveStartTableName`` parameter in a subsequent ``list-tables`` request and obtain the next page of results.

  

  (string)

    

    

  

LastEvaluatedTableName -> (string)

  

  The name of the last table in the current page of results. Use this value as the ``ExclusiveStartTableName`` in a new request to obtain the next page of results, until all the table names are returned.

   

  If you do not receive a ``LastEvaluatedTableName`` value in the response, this means that there are no more table names to be retrieved.

  

  

