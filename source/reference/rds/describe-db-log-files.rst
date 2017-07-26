[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-db-log-files:


*********************
describe-db-log-files
*********************



===========
Description
===========



Returns a list of DB log files for the DB instance. 



``describe-db-log-files`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``DescribeDBLogFiles``


========
Synopsis
========

::

    describe-db-log-files
  --db-instance-identifier <value>
  [--filename-contains <value>]
  [--file-last-written <value>]
  [--file-size <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-instance-identifier`` (string)


  The customer-assigned name of the DB instance that contains the log files you want to list. 

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  

``--filename-contains`` (string)


  Filters the available log files for log file names that contain the specified string. 

  

``--file-last-written`` (long)


  Filters the available log files for files written since the specified date, in POSIX timestamp format with milliseconds. 

  

``--file-size`` (long)


  Filters the available log files for files larger than the specified size. 

  

``--filters`` (list)


  This parameter is not currently supported.

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



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



======
Output
======

DescribeDBLogFiles -> (list)

  

  The DB log files returned. 

  

  (structure)

    

    This data type is used as a response element to  describe-db-log-files .

    

    LogFileName -> (string)

      

      The name of the log file for the specified DB instance. 

      

      

    LastWritten -> (long)

      

      A POSIX timestamp when the last log entry was written. 

      

      

    Size -> (long)

      

      The size, in bytes, of the log file for the specified DB instance. 

      

      

    

  

Marker -> (string)

  

  A pagination token that can be used in a subsequent describe-db-log-files request. 

  

  

