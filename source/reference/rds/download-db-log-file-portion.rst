[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds download-db-log-file-portion:


****************************
download-db-log-file-portion
****************************



===========
Description
===========



Downloads all or a portion of the specified log file, up to 1 MB in size.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DownloadDBLogFilePortion>`_


``download-db-log-file-portion`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``LogFileData``


========
Synopsis
========

::

    download-db-log-file-portion
  --db-instance-identifier <value>
  --log-file-name <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-instance-identifier`` (string)


  The customer-assigned name of the DB instance that contains the log files you want to list.

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens 
   
  * First character must be a letter 
   
  * Cannot end with a hyphen or contain two consecutive hyphens 
   

  

``--log-file-name`` (string)


  The name of the log file to be downloaded.

  

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

**How to download your log file**

By default, this command will only download the latest part of your log file::

    aws rds download-db-log-file-portion --db-instance-identifier myinstance \
    --log-file-name log.txt --output text > tail.txt

In order to download the entire file, you need `--starting-token 0` parameter::

    aws rds download-db-log-file-portion --db-instance-identifier myinstance \
    --log-file-name log.txt --starting-token 0 --output text > full.txt

Note that, the downloaded file may contain several extra blank lines.
They appear at the end of each part of the log file while being downloaded.
This will generally not cause any trouble in your log file analysis.


======
Output
======

LogFileData -> (string)

  

  Entries from the specified log file.

  

  

Marker -> (string)

  

  A pagination token that can be used in a subsequent download-db-log-file-portion request.

  

  

AdditionalDataPending -> (boolean)

  

  Boolean value that if true, indicates there is more data to be downloaded.

  

  

