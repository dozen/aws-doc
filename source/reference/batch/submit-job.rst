[ :ref:`aws <cli:aws>` . :ref:`batch <cli:aws batch>` ]

.. _cli:aws batch submit-job:


**********
submit-job
**********



===========
Description
===========



Submits an AWS Batch job from a job definition. Parameters specified during  submit-job override parameters defined in the job definition. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/batch-2016-08-10/SubmitJob>`_


========
Synopsis
========

::

    submit-job
  --job-name <value>
  --job-queue <value>
  [--depends-on <value>]
  --job-definition <value>
  [--parameters <value>]
  [--container-overrides <value>]
  [--retry-strategy <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-name`` (string)


  The name of the job. A name must be 1 to 128 characters in length.

   

  Pattern: ^[a-zA-Z0-9_]+$

  

``--job-queue`` (string)


  The job queue into which the job will be submitted. You can specify either the name or the Amazon Resource Name (ARN) of the queue. 

  

``--depends-on`` (list)


  A list of job IDs on which this job depends. A job can depend upon a maximum of 100 jobs. 

  



Shorthand Syntax::

    jobId=string ...




JSON Syntax::

  [
    {
      "jobId": "string"
    }
    ...
  ]



``--job-definition`` (string)


  The job definition used by this job. This value can be either a ``name:revision`` or the Amazon Resource Name (ARN) for the job definition.

  

``--parameters`` (map)


  Additional parameters passed to the job that replace parameter substitution placeholders that are set in the job definition. Parameters are specified as a key and value pair mapping. Parameters in a ``submit-job`` request override any corresponding parameter defaults from the job definition.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--container-overrides`` (structure)


  A list of container overrides in JSON format that specify the name of a container in the specified job definition and the overrides it should receive. You can override the default command for a container (that is specified in the job definition or the Docker image) with a ``command`` override. You can also override existing environment variables (that are specified in the job definition or Docker image) on a container or add new environment variables to it with an ``environment`` override.

  



Shorthand Syntax::

    vcpus=integer,memory=integer,command=string,string,environment=[{name=string,value=string},{name=string,value=string}]




JSON Syntax::

  {
    "vcpus": integer,
    "memory": integer,
    "command": ["string", ...],
    "environment": [
      {
        "name": "string",
        "value": "string"
      }
      ...
    ]
  }



``--retry-strategy`` (structure)


  The retry strategy to use for failed jobs from this  submit-job operation. When a retry strategy is specified here, it overrides the retry strategy defined in the job definition.

  



Shorthand Syntax::

    attempts=integer




JSON Syntax::

  {
    "attempts": integer
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To submit a job**

This example submits a simple container job called `example` to the `HighPriority` job queue.

Command::

  aws batch submit-job --job-name example --job-queue HighPriority  --job-definition sleep60

Output::

  {
      "jobName": "example",
      "jobId": "876da822-4198-45f2-a252-6cea32512ea8"
  }


======
Output
======

jobName -> (string)

  

  The name of the job. 

  

  

jobId -> (string)

  

  The unique identifier for the job.

  

  

