[ :ref:`aws <cli:aws>` . :ref:`batch <cli:aws batch>` ]

.. _cli:aws batch describe-jobs:


*************
describe-jobs
*************



===========
Description
===========



Describes a list of AWS Batch jobs.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/batch-2016-08-10/DescribeJobs>`_


========
Synopsis
========

::

    describe-jobs
  --jobs <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--jobs`` (list)


  A space-separated list of up to 100 job IDs.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a job**

This example describes a job with the specified job ID.

Command::

  aws batch describe-jobs --jobs bcf0b186-a532-4122-842e-2ccab8d54efb

Output::

	{
	    "jobs": [
	        {
	            "status": "SUBMITTED",
	            "container": {
	                "mountPoints": [],
	                "image": "busybox",
	                "environment": [],
	                "vcpus": 1,
	                "command": [
	                    "sleep",
	                    "60"
	                ],
	                "volumes": [],
	                "memory": 128,
	                "ulimits": []
	            },
	            "parameters": {},
	            "jobDefinition": "sleep60",
	            "jobQueue": "arn:aws:batch:us-east-1:012345678910:job-queue/HighPriority",
	            "jobId": "bcf0b186-a532-4122-842e-2ccab8d54efb",
	            "dependsOn": [],
	            "jobName": "example",
	            "createdAt": 1480483387803
	        }
	    ]
	}


======
Output
======

jobs -> (list)

  

  The list of jobs. 

  

  (structure)

    

    An object representing an AWS Batch job.

    

    jobName -> (string)

      

      The name of the job.

      

      

    jobId -> (string)

      

      The ID for the job.

      

      

    jobQueue -> (string)

      

      The Amazon Resource Name (ARN) of the job queue with which the job is associated.

      

      

    status -> (string)

      

      The current status for the job.

      

      

    attempts -> (list)

      

      A list of job attempts associated with this job.

      

      (structure)

        

        An object representing a job attempt.

        

        container -> (structure)

          

          Details about the container in this job attempt.

          

          containerInstanceArn -> (string)

            

            The Amazon Resource Name (ARN) of the Amazon ECS container instance that hosts the job attempt.

            

            

          taskArn -> (string)

            

            The Amazon Resource Name (ARN) of the Amazon ECS task that is associated with the job attempt.

            

            

          exitCode -> (integer)

            

            The exit code for the job attempt. A non-zero exit code is considered a failure.

            

            

          reason -> (string)

            

            A short (255 max characters) human-readable string to provide additional details about a running or stopped container.

            

            

          

        startedAt -> (long)

          

          The Unix timestamp for when the attempt was started (when the task transitioned from the ``PENDING`` state to the ``RUNNING`` state).

          

          

        stoppedAt -> (long)

          

          The Unix timestamp for when the attempt was stopped (when the task transitioned from the ``RUNNING`` state to the ``STOPPED`` state).

          

          

        statusReason -> (string)

          

          A short, human-readable string to provide additional details about the current status of the job attempt.

          

          

        

      

    statusReason -> (string)

      

      A short, human-readable string to provide additional details about the current status of the job. 

      

      

    createdAt -> (long)

      

      The Unix timestamp for when the job was created (when the task entered the ``PENDING`` state). 

      

      

    retryStrategy -> (structure)

      

      The retry strategy to use for this job if an attempt fails.

      

      attempts -> (integer)

        

        The number of times to move a job to the ``RUNNABLE`` status. You may specify between 1 and 10 attempts. If ``attempts`` is greater than one, the job is retried if it fails until it has moved to ``RUNNABLE`` that many times.

        

        

      

    startedAt -> (long)

      

      The Unix timestamp for when the job was started (when the task transitioned from the ``PENDING`` state to the ``RUNNING`` state). 

      

      

    stoppedAt -> (long)

      

      The Unix timestamp for when the job was stopped (when the task transitioned from the ``RUNNING`` state to the ``STOPPED`` state).

      

      

    dependsOn -> (list)

      

      A list of job names or IDs on which this job depends.

      

      (structure)

        

        An object representing an AWS Batch job dependency.

        

        jobId -> (string)

          

          The job ID of the AWS Batch job associated with this dependency.

          

          

        

      

    jobDefinition -> (string)

      

      The job definition that is used by this job.

      

      

    parameters -> (map)

      

      Additional parameters passed to the job that replace parameter substitution placeholders or override any corresponding parameter defaults from the job definition. 

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    container -> (structure)

      

      An object representing the details of the container that is associated with the job.

      

      image -> (string)

        

        The image used to start the container.

        

        

      vcpus -> (integer)

        

        The number of VCPUs allocated for the job. 

        

        

      memory -> (integer)

        

        The number of MiB of memory reserved for the job.

        

        

      command -> (list)

        

        The command that is passed to the container. 

        

        (string)

          

          

        

      jobRoleArn -> (string)

        

        The Amazon Resource Name (ARN) associated with the job upon execution. 

        

        

      volumes -> (list)

        

        A list of volumes associated with the job.

        

        (structure)

          

          A data volume used in a job's container properties.

          

          host -> (structure)

            

            The contents of the ``host`` parameter determine whether your data volume persists on the host container instance and where it is stored. If the host parameter is empty, then the Docker daemon assigns a host path for your data volume, but the data is not guaranteed to persist after the containers associated with it stop running.

            

            sourcePath -> (string)

              

              The path on the host container instance that is presented to the container. If this parameter is empty, then the Docker daemon has assigned a host path for you. If the ``host`` parameter contains a ``sourcePath`` file location, then the data volume persists at the specified location on the host container instance until you delete it manually. If the ``sourcePath`` value does not exist on the host container instance, the Docker daemon creates it. If the location does exist, the contents of the source path folder are exported.

              

              

            

          name -> (string)

            

            The name of the volume. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. This name is referenced in the ``sourceVolume`` parameter of container definition ``mountPoints`` .

            

            

          

        

      environment -> (list)

        

        The environment variables to pass to a container.

        

        (structure)

          

          A key-value pair object.

          

          name -> (string)

            

            The name of the key value pair. For environment variables, this is the name of the environment variable.

            

            

          value -> (string)

            

            The value of the key value pair. For environment variables, this is the value of the environment variable.

            

            

          

        

      mountPoints -> (list)

        

        The mount points for data volumes in your container.

        

        (structure)

          

          Details on a Docker volume mount point that is used in a job's container properties.

          

          containerPath -> (string)

            

            The path on the container at which to mount the host volume.

            

            

          readOnly -> (boolean)

            

            If this value is ``true`` , the container has read-only access to the volume; otherwise, the container can write to the volume. The default value is ``false`` .

            

            

          sourceVolume -> (string)

            

            The name of the volume to mount.

            

            

          

        

      readonlyRootFilesystem -> (boolean)

        

        When this parameter is true, the container is given read-only access to its root file system.

        

        

      ulimits -> (list)

        

        A list of ``ulimit`` values to set in the container.

        

        (structure)

          

          The ``ulimit`` settings to pass to the container.

          

          hardLimit -> (integer)

            

            The hard limit for the ``ulimit`` type.

            

            

          name -> (string)

            

            The ``type`` of the ``ulimit`` .

            

            

          softLimit -> (integer)

            

            The soft limit for the ``ulimit`` type.

            

            

          

        

      privileged -> (boolean)

        

        When this parameter is true, the container is given elevated privileges on the host container instance (similar to the ``root`` user).

        

        

      user -> (string)

        

        The user name to use inside the container.

        

        

      exitCode -> (integer)

        

        The exit code to return upon completion.

        

        

      reason -> (string)

        

        A short (255 max characters) human-readable string to provide additional details about a running or stopped container.

        

        

      containerInstanceArn -> (string)

        

        The Amazon Resource Name (ARN) of the container instance on which the container is running.

        

        

      taskArn -> (string)

        

        The Amazon Resource Name (ARN) of the Amazon ECS task that is associated with the container job.

        

        

      

    

  

