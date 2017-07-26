[ :ref:`aws <cli:aws>` . :ref:`snowball <cli:aws snowball>` ]

.. _cli:aws snowball list-cluster-jobs:


*****************
list-cluster-jobs
*****************



===========
Description
===========



Returns an array of ``JobListEntry`` objects of the specified length. Each ``JobListEntry`` object is for a job in the specified cluster and contains a job's state, a job's ID, and other information.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/snowball-2016-06-30/ListClusterJobs>`_


========
Synopsis
========

::

    list-cluster-jobs
  --cluster-id <value>
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-id`` (string)


  The 39-character ID for the cluster that you want to list, for example ``CID123e4567-e89b-12d3-a456-426655440000`` .

  

``--max-results`` (integer)


  The number of ``JobListEntry`` objects to return.

  

``--next-token`` (string)


  HTTP requests are stateless. To identify what object comes "next" in the list of ``JobListEntry`` objects, you have the option of specifying ``NextToken`` as the starting point for your returned list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

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

  

  HTTP requests are stateless. If you use the automatically generated ``NextToken`` value in your next ``ListClusterJobsResult`` call, your list of returned jobs will start from this point in the array.

  

  

