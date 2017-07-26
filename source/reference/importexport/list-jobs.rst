[ :ref:`aws <cli:aws>` . :ref:`importexport <cli:aws importexport>` ]

.. _cli:aws importexport list-jobs:


*********
list-jobs
*********



===========
Description
===========

This operation returns the jobs associated with the requester. AWS Import/Export lists the jobs in reverse chronological order based on the date of creation. For example if Job Test1 was created 2009Dec30 and Test2 was created 2010Feb05, the list-jobs operation would return Test2 followed by Test1.

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
  [--generate-cli-skeleton]




=======
Options
=======

``--api-version`` (string)
Specifies the version of the client tool.

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

  

