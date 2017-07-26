[ :ref:`aws <cli:aws>` . :ref:`batch <cli:aws batch>` ]

.. _cli:aws batch update-compute-environment:


**************************
update-compute-environment
**************************



===========
Description
===========



Updates an AWS Batch compute environment.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/batch-2016-08-10/UpdateComputeEnvironment>`_


========
Synopsis
========

::

    update-compute-environment
  --compute-environment <value>
  [--state <value>]
  [--compute-resources <value>]
  [--service-role <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--compute-environment`` (string)


  The name or full Amazon Resource Name (ARN) of the compute environment to update.

  

``--state`` (string)


  The state of the compute environment. Compute environments in the ``ENABLED`` state can accept jobs from a queue and scale in or out automatically based on the workload demand of its associated queues.

  

  Possible values:

  
  *   ``ENABLED``

  
  *   ``DISABLED``

  

  

``--compute-resources`` (structure)


  Details of the compute resources managed by the compute environment. Required for a managed compute environment.

  



Shorthand Syntax::

    minvCpus=integer,maxvCpus=integer,desiredvCpus=integer




JSON Syntax::

  {
    "minvCpus": integer,
    "maxvCpus": integer,
    "desiredvCpus": integer
  }



``--service-role`` (string)


  The name or full Amazon Resource Name (ARN) of the IAM role that allows AWS Batch to make calls to ECS, Auto Scaling, and EC2 on your behalf.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To update a compute environment**

This example disables the `P2OnDemand` compute environment so it can be deleted.

Command::

  aws batch update-compute-environment --compute-environment P2OnDemand --state DISABLED

Output::

	{
	    "computeEnvironmentName": "P2OnDemand",
	    "computeEnvironmentArn": "arn:aws:batch:us-east-1:012345678910:compute-environment/P2OnDemand"
	}


======
Output
======

computeEnvironmentName -> (string)

  

  The name of compute environment.

  

  

computeEnvironmentArn -> (string)

  

  The Amazon Resource Name (ARN) of the compute environment. 

  

  

