[ :ref:`aws <cli:aws>` . :ref:`cur <cli:aws cur>` ]

.. _cli:aws cur describe-report-definitions:


***************************
describe-report-definitions
***************************



===========
Description
===========

Describe a list of report definitions owned by the account

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cur-2017-01-06/DescribeReportDefinitions>`_


``describe-report-definitions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ReportDefinitions``


========
Synopsis
========

::

    describe-report-definitions
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



======
Output
======

ReportDefinitions -> (list)

  A list of report definitions.

  (structure)

    The definition of AWS Cost and Usage Report. Customer can specify the report name, time unit, report format, compression format, S3 bucket and additional artifacts and schema elements in the definition.

    ReportName -> (string)

      Preferred name for a report, it has to be unique. Must starts with a number/letter, case sensitive. Limited to 256 characters.

      

    TimeUnit -> (string)

      The frequency on which report data are measured and displayed.

      

    Format -> (string)

      Preferred format for report.

      

    Compression -> (string)

      Preferred compression format for report.

      

    AdditionalSchemaElements -> (list)

      A list of schema elements.

      (string)

        Preference of including Resource IDs. You can include additional details about individual resource IDs in your report.

        

      

    S3Bucket -> (string)

      Name of customer S3 bucket.

      

    S3Prefix -> (string)

      Preferred report path prefix. Limited to 256 characters.

      

    S3Region -> (string)

      Region of customer S3 bucket.

      

    AdditionalArtifacts -> (list)

      A list of additional artifacts.

      (string)

        Enable support for Redshift and/or QuickSight.

        

      

    

  

NextToken -> (string)

  A generic string.

  

