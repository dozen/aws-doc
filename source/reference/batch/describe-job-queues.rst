[ :ref:`aws <cli:aws>` . :ref:`batch <cli:aws batch>` ]

.. _cli:aws batch describe-job-queues:


*******************
describe-job-queues
*******************



===========
Description
===========



Describes one or more of your job queues.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/batch-2016-08-10/DescribeJobQueues>`_


========
Synopsis
========

::

    describe-job-queues
  [--job-queues <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-queues`` (list)


  A list of up to 100 queue names or full queue Amazon Resource Name (ARN) entries.

  



Syntax::

  "string" "string" ...



``--max-results`` (integer)


  The maximum number of results returned by ``describe-job-queues`` in paginated output. When this parameter is used, ``describe-job-queues`` only returns ``maxResults`` results in a single page along with a ``nextToken`` response element. The remaining results of the initial request can be seen by sending another ``describe-job-queues`` request with the returned ``nextToken`` value. This value can be between 1 and 100. If this parameter is not used, then ``describe-job-queues`` returns up to 100 results and a ``nextToken`` value if applicable.

  

``--next-token`` (string)


  The ``nextToken`` value returned from a previous paginated ``describe-job-queues`` request where ``maxResults`` was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the ``nextToken`` value. This value is ``null`` when there are no more results to return.

   

  .. note::

     

    This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes.

     

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a job queue**

This example describes the `HighPriority` job queue.

Command::

  aws batch describe-job-queues --job-queues HighPriority

Output::

	{
	    "jobQueues": [
	        {
	            "status": "VALID",
	            "jobQueueArn": "arn:aws:batch:us-east-1:012345678910:job-queue/HighPriority",
	            "computeEnvironmentOrder": [
	                {
	                    "computeEnvironment": "arn:aws:batch:us-east-1:012345678910:compute-environment/C4OnDemand",
	                    "order": 1
	                }
	            ],
	            "statusReason": "JobQueue Healthy",
	            "priority": 1,
	            "state": "ENABLED",
	            "jobQueueName": "HighPriority"
	        }
	    ]
	}


======
Output
======

jobQueues -> (list)

  

  The list of job queues. 

  

  (structure)

    

    An object representing the details of an AWS Batch job queue.

    

    jobQueueName -> (string)

      

      The name of the job queue.

      

      

    jobQueueArn -> (string)

      

      The Amazon Resource Name (ARN) of the job queue.

      

      

    state -> (string)

      

      Describes the ability of the queue to accept new jobs.

      

      

    status -> (string)

      

      The status of the job queue (for example, ``CREATING`` or ``VALID`` ).

      

      

    statusReason -> (string)

      

      A short, human-readable string to provide additional details about the current status of the job queue.

      

      

    priority -> (integer)

      

      The priority of the job queue. 

      

      

    computeEnvironmentOrder -> (list)

      

      The compute environments that are attached to the job queue and the order in which job placement is preferred. Compute environments are selected for job placement in ascending order.

      

      (structure)

        

        The order in which compute environments are tried for job placement within a queue. Compute environments are tried in ascending order. For example, if two compute environments are associated with a job queue, the compute environment with a lower order integer value is tried for job placement first.

        

        order -> (integer)

          

          The order of the compute environment.

          

          

        computeEnvironment -> (string)

          

          The Amazon Resource Name (ARN) of the compute environment.

          

          

        

      

    

  

nextToken -> (string)

  

  The ``nextToken`` value to include in a future ``describe-job-queues`` request. When the results of a ``describe-job-queues`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

