[ :ref:`aws <cli:aws>` . :ref:`batch <cli:aws batch>` ]

.. _cli:aws batch create-job-queue:


****************
create-job-queue
****************



===========
Description
===========



Creates an AWS Batch job queue. When you create a job queue, you associate one or more compute environments to the queue and assign an order of preference for the compute environments.

 

You also set a priority to the job queue that determines the order in which the AWS Batch scheduler places jobs onto its associated compute environments. For example, if a compute environment is associated with more than one job queue, the job queue with a higher priority is given preference for scheduling jobs to that compute environment.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/batch-2016-08-10/CreateJobQueue>`_


========
Synopsis
========

::

    create-job-queue
  --job-queue-name <value>
  [--state <value>]
  --priority <value>
  --compute-environment-order <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-queue-name`` (string)


  The name of the job queue.

  

``--state`` (string)


  The state of the job queue. If the job queue state is ``ENABLED`` , it is able to accept jobs.

  

  Possible values:

  
  *   ``ENABLED``

  
  *   ``DISABLED``

  

  

``--priority`` (integer)


  The priority of the job queue. Job queues with a higher priority (or a lower integer value for the ``priority`` parameter) are evaluated first when associated with same compute environment. Priority is determined in ascending order, for example, a job queue with a priority value of ``1`` is given scheduling preference over a job queue with a priority value of ``10`` .

  

``--compute-environment-order`` (list)


  The set of compute environments mapped to a job queue and their order relative to each other. The job scheduler uses this parameter to determine which compute environment should execute a given job. Compute environments must be in the ``VALID`` state before you can associate them with a job queue. You can associate up to 3 compute environments with a job queue.

  



Shorthand Syntax::

    order=integer,computeEnvironment=string ...




JSON Syntax::

  [
    {
      "order": integer,
      "computeEnvironment": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a low priority job queue with a single compute environment**

This example creates a job queue called `LowPriority` that uses the `M4Spot` compute environment.

Command::

  aws batch create-job-queue --cli-input-json file://<path_to_json_file>/LowPriority.json
  
JSON file format::

  {
    "jobQueueName": "LowPriority",
    "state": "ENABLED",
    "priority": 10,
    "computeEnvironmentOrder": [
      {
        "order": 1,
        "computeEnvironment": "M4Spot"
      }
    ]
  }

Output::

  {
      "jobQueueArn": "arn:aws:batch:us-east-1:012345678910:job-queue/LowPriority",
      "jobQueueName": "LowPriority"
  }

**To create a high priority job queue with two compute environments**

This example creates a job queue called `HighPriority` that uses the `C4OnDemand` compute environment with an order of 1 and the `M4Spot` compute environment with an order of 2. The scheduler will attempt to place jobs on the `C4OnDemand` compute environment first.

Command::

  aws batch create-job-queue --cli-input-json file://<path_to_json_file>/HighPriority.json
  
JSON file format::

  {
    "jobQueueName": "HighPriority",
    "state": "ENABLED",
    "priority": 1,
    "computeEnvironmentOrder": [
      {
        "order": 1,
        "computeEnvironment": "C4OnDemand"
      },
      {
        "order": 2,
        "computeEnvironment": "M4Spot"
      }
    ]
  }

Output::

  {
      "jobQueueArn": "arn:aws:batch:us-east-1:012345678910:job-queue/HighPriority",
      "jobQueueName": "HighPriority"
  }


======
Output
======

jobQueueName -> (string)

  

  The name of the job queue.

  

  

jobQueueArn -> (string)

  

  The Amazon Resource Name (ARN) of the job queue.

  

  

