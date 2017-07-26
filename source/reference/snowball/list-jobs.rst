[ :ref:`aws <cli:aws>` . :ref:`snowball <cli:aws snowball>` ]

.. _cli:aws snowball list-jobs:


*********
list-jobs
*********



===========
Description
===========



Returns an array of ``JobListEntry`` objects of the specified length. Each ``JobListEntry`` object contains a job's state, a job's ID, and a value that indicates whether the job is a job part, in the case of export jobs. Calling this API action in one of the US regions will return jobs from the list of all jobs associated with this account in all US regions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/snowball-2016-06-30/ListJobs>`_


``list-jobs`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``JobListEntries``


========
Synopsis
========

::

    list-jobs
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

JobListEntries -> (list)

  

  Each ``JobListEntry`` object contains a job's state, a job's ID, and a value that indicates whether the job is a job part, in the case of export jobs. 

  

  (structure)

    

    Each ``JobListEntry`` object contains a job's state, a job's ID, and a value that indicates whether the job is a job part, in the case of an export job.

    

    JobId -> (string)

      

      The automatically generated ID for a job, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

      

      

    JobState -> (string)

      

      The current state of this job.

      

      

    IsMaster -> (boolean)

      

      A value that indicates that this job is a master job. A master job represents a successful request to create an export job. Master jobs aren't associated with any Snowballs. Instead, each master job will have at least one job part, and each job part is associated with a Snowball. It might take some time before the job parts associated with a particular master job are listed, because they are created after the master job is created.

      

      

    JobType -> (string)

      

      The type of job.

      

      

    SnowballType -> (string)

      

      The type of appliance used with this job.

      

      

    CreationDate -> (timestamp)

      

      The creation date for this job.

      

      

    Description -> (string)

      

      The optional description of this specific job, for example ``Important Photos 2016-08-11`` .

      

      

    

  

NextToken -> (string)

  

  HTTP requests are stateless. If you use this automatically generated ``NextToken`` value in your next ``list-jobs`` call, your returned ``JobListEntry`` objects will start from this point in the array.

  

  

