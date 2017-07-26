[ :ref:`aws <cli:aws>` . :ref:`batch <cli:aws batch>` ]

.. _cli:aws batch list-jobs:


*********
list-jobs
*********



===========
Description
===========



Returns a list of task jobs for a specified job queue. You can filter the results by job status with the ``jobStatus`` parameter.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/batch-2016-08-10/ListJobs>`_


========
Synopsis
========

::

    list-jobs
  --job-queue <value>
  [--job-status <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-queue`` (string)


  The name or full Amazon Resource Name (ARN) of the job queue with which to list jobs.

  

``--job-status`` (string)


  The job status with which to filter jobs in the specified queue.

  

  Possible values:

  
  *   ``SUBMITTED``

  
  *   ``PENDING``

  
  *   ``RUNNABLE``

  
  *   ``STARTING``

  
  *   ``RUNNING``

  
  *   ``SUCCEEDED``

  
  *   ``FAILED``

  

  

``--max-results`` (integer)


  The maximum number of results returned by ``list-jobs`` in paginated output. When this parameter is used, ``list-jobs`` only returns ``maxResults`` results in a single page along with a ``nextToken`` response element. The remaining results of the initial request can be seen by sending another ``list-jobs`` request with the returned ``nextToken`` value. This value can be between 1 and 100. If this parameter is not used, then ``list-jobs`` returns up to 100 results and a ``nextToken`` value if applicable.

  

``--next-token`` (string)


  The ``nextToken`` value returned from a previous paginated ``list-jobs`` request where ``maxResults`` was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the ``nextToken`` value. This value is ``null`` when there are no more results to return.

   

  .. note::

     

    This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes.

     

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list running jobs**

This example lists the running jobs in the `HighPriority` job queue.

Command::

  aws batch list-jobs --job-queue HighPriority

Output::

  {
      "jobSummaryList": [
          {
              "jobName": "example",
              "jobId": "e66ff5fd-a1ff-4640-b1a2-0b0a142f49bb"
          }
      ]
  }


**To list submitted jobs**

This example lists jobs in the `HighPriority` job queue that are in the `SUBMITTED` job status.

Command::

  aws batch list-jobs --job-queue HighPriority --job-status SUBMITTED

Output::

  {
      "jobSummaryList": [
          {
              "jobName": "example",
              "jobId": "68f0c163-fbd4-44e6-9fd1-25b14a434786"
          }
      ]
  }
  

======
Output
======

jobSummaryList -> (list)

  

  A list of job summaries that match the request.

  

  (structure)

    

    An object representing summary details of a job.

    

    jobId -> (string)

      

      The ID of the job.

      

      

    jobName -> (string)

      

      The name of the job.

      

      

    

  

nextToken -> (string)

  

  The ``nextToken`` value to include in a future ``list-jobs`` request. When the results of a ``list-jobs`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

