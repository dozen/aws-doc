[ :ref:`aws <cli:aws>` . :ref:`importexport <cli:aws importexport>` ]

.. _cli:aws importexport list-jobs:


*********
list-jobs
*********



===========
Description
===========

This operation returns the jobs associated with the requester. AWS Import/Export lists the jobs in reverse chronological order based on the date of creation. For example if Job Test1 was created 2009Dec30 and Test2 was created 2010Feb05, the list-jobs operation would return Test2 followed by Test1.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/importexport-2010-06-01/ListJobs>`_


``list-jobs`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Jobs``


========
Synopsis
========

::

    list-jobs
  [--api-version <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--api-version`` (string)
Specifies the version of the client tool.

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

The following command lists the jobs you've created::

  aws importexport list-jobs

The output for the list-jobs command looks like the following::

  JOBS    2015-05-27T18:58:21Z    False   EX1ID   Import

You can only list jobs created by users under the AWS account you are currently using. Listing jobs returns useful information, like job IDs, which are necessary for other AWS Import/Export commands.


======
Output
======

Jobs -> (list)

  A list container for Jobs returned by the list-jobs operation.

  (structure)

    Representation of a job returned by the list-jobs operation.

    JobId -> (string)

      A unique identifier which refers to a particular job.

      

    CreationDate -> (timestamp)

      Timestamp of the create-job request in ISO8601 date format. For example "2010-03-28T20:27:35Z".

      

    IsCanceled -> (boolean)

      Indicates whether the job was canceled.

      

    JobType -> (string)

      Specifies whether the job to initiate is an import or export job.

      

    

  

IsTruncated -> (boolean)

  Indicates whether the list of jobs was truncated. If true, then call list-jobs again using the last JobId element as the marker.

  

