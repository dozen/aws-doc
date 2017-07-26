[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb list-tables:


***********
list-tables
***********



===========
Description
===========



Returns an array of table names associated with the current account and endpoint. The output from *list-tables* is paginated, with each page returning a maximum of 100 table names.



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
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

   

  If *LastEvaluatedTableName* also appears in the output, you can use this value as the *ExclusiveStartTableName* parameter in a subsequent *list-tables* request and obtain the next page of results.

  

  (string)

    

    

  

LastEvaluatedTableName -> (string)

  

  The name of the last table in the current page of results. Use this value as the *ExclusiveStartTableName* in a new request to obtain the next page of results, until all the table names are returned.

   

  If you do not receive a *LastEvaluatedTableName* value in the response, this means that there are no more table names to be retrieved.

  

  

