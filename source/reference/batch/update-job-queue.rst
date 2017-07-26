[ :ref:`aws <cli:aws>` . :ref:`batch <cli:aws batch>` ]

.. _cli:aws batch update-job-queue:


****************
update-job-queue
****************



===========
Description
===========



Updates a job queue.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/batch-2016-08-10/UpdateJobQueue>`_


========
Synopsis
========

::

    update-job-queue
  --job-queue <value>
  [--state <value>]
  [--priority <value>]
  [--compute-environment-order <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-queue`` (string)


  The name or the Amazon Resource Name (ARN) of the job queue.

  

``--state`` (string)


  Describes the queue's ability to accept new jobs.

  

  Possible values:

  
  *   ``ENABLED``

  
  *   ``DISABLED``

  

  

``--priority`` (integer)


  The priority of the job queue. Job queues with a higher priority (or a lower integer value for the ``priority`` parameter) are evaluated first when associated with same compute environment. Priority is determined in ascending order, for example, a job queue with a priority value of ``1`` is given scheduling preference over a job queue with a priority value of ``10`` .

  

``--compute-environment-order`` (list)


  Details the set of compute environments mapped to a job queue and their order relative to each other. This is one of the parameters used by the job scheduler to determine which compute environment should execute a given job. 

  



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

**To update a job queue**

This example disables a job queue so that it can be deleted.

Command::

  aws batch update-job-queue --job-queue GPGPU --state DISABLE

Output::

	{
	    "jobQueueArn": "arn:aws:batch:us-east-1:012345678910:job-queue/GPGPU",
	    "jobQueueName": "GPGPU"
	}


======
Output
======

jobQueueName -> (string)

  

  The name of the job queue.

  

  

jobQueueArn -> (string)

  

  The Amazon Resource Name (ARN) of the job queue.

  

  

