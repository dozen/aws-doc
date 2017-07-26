[ :ref:`aws <cli:aws>` . :ref:`batch <cli:aws batch>` ]

.. _cli:aws batch describe-job-definitions:


************************
describe-job-definitions
************************



===========
Description
===========



Describes a list of job definitions. You can specify a ``status`` (such as ``ACTIVE`` ) to only return job definitions that match that status.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/batch-2016-08-10/DescribeJobDefinitions>`_


========
Synopsis
========

::

    describe-job-definitions
  [--job-definitions <value>]
  [--max-results <value>]
  [--job-definition-name <value>]
  [--status <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-definitions`` (list)


  A space-separated list of up to 100 job definition names or full Amazon Resource Name (ARN) entries.

  



Syntax::

  "string" "string" ...



``--max-results`` (integer)


  The maximum number of results returned by ``describe-job-definitions`` in paginated output. When this parameter is used, ``describe-job-definitions`` only returns ``maxResults`` results in a single page along with a ``nextToken`` response element. The remaining results of the initial request can be seen by sending another ``describe-job-definitions`` request with the returned ``nextToken`` value. This value can be between 1 and 100. If this parameter is not used, then ``describe-job-definitions`` returns up to 100 results and a ``nextToken`` value if applicable.

  

``--job-definition-name`` (string)


  The name of the job definition to describe.

  

``--status`` (string)


  The status with which to filter job definitions.

  

``--next-token`` (string)


  The ``nextToken`` value returned from a previous paginated ``describe-job-definitions`` request where ``maxResults`` was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the ``nextToken`` value. This value is ``null`` when there are no more results to return.

   

  .. note::

     

    This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes.

     

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe active job definitions**

This example describes all of your active job definitions.

Command::

  aws batch describe-job-definitions --status ACTIVE

Output::

  {
      "jobDefinitions": [
          {
              "status": "ACTIVE",
              "jobDefinitionArn": "arn:aws:batch:us-east-1:012345678910:job-definition/sleep60:1",
              "containerProperties": {
                  "mountPoints": [],
                  "parameters": {},
                  "image": "busybox",
                  "environment": {},
                  "vcpus": 1,
                  "command": [
                      "sleep",
                      "60"
                  ],
                  "volumes": [],
                  "memory": 128,
                  "ulimits": []
              },
              "type": "container",
              "jobDefinitionName": "sleep60",
              "revision": 1
          }
      ]
  }


======
Output
======

jobDefinitions -> (list)

  

  The list of job definitions. 

  

  (structure)

    

    An object representing an AWS Batch job definition.

    

    jobDefinitionName -> (string)

      

      The name of the job definition. 

      

      

    jobDefinitionArn -> (string)

      

      The Amazon Resource Name (ARN) for the job definition. 

      

      

    revision -> (integer)

      

      The revision of the job definition.

      

      

    status -> (string)

      

      The status of the job definition.

      

      

    type -> (string)

      

      The type of job definition.

      

      

    parameters -> (map)

      

      Default parameters or parameter substitution placeholders that are set in the job definition. Parameters are specified as a key-value pair mapping. Parameters in a ``submit-job`` request override any corresponding parameter defaults from the job definition.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    retryStrategy -> (structure)

      

      The retry strategy to use for failed jobs that are submitted with this job definition.

      

      attempts -> (integer)

        

        The number of times to move a job to the ``RUNNABLE`` status. You may specify between 1 and 10 attempts. If ``attempts`` is greater than one, the job is retried if it fails until it has moved to ``RUNNABLE`` that many times.

        

        

      

    containerProperties -> (structure)

      

      An object with various properties specific to container-based jobs. 

      

      image -> (string)

        

        The image used to start a container. This string is passed directly to the Docker daemon. Images in the Docker Hub registry are available by default. Other repositories are specified with `` *repository-url* /*image* :*tag* `` . Up to 255 letters (uppercase and lowercase), numbers, hyphens, underscores, colons, periods, forward slashes, and number signs are allowed. This parameter maps to ``Image`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``IMAGE`` parameter of `docker run <https://docs.docker.com/engine/reference/run/>`_ .

         

         
        * Images in Amazon ECR repositories use the full registry and repository URI (for example, ``012345678910.dkr.ecr.region-name.amazonaws.com/repository-name`` ).  
         
        * Images in official repositories on Docker Hub use a single name (for example, ``ubuntu`` or ``mongo`` ). 
         
        * Images in other repositories on Docker Hub are qualified with an organization name (for example, ``amazon/amazon-ecs-agent`` ). 
         
        * Images in other online repositories are qualified further by a domain name (for example, ``quay.io/assemblyline/ubuntu`` ). 
         

        

        

      vcpus -> (integer)

        

        The number of vCPUs reserved for the container. This parameter maps to ``CpuShares`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--cpu-shares`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ . Each vCPU is equivalent to 1,024 CPU shares.

        

        

      memory -> (integer)

        

        The hard limit (in MiB) of memory to present to the container. If your container attempts to exceed the memory specified here, the container is killed. This parameter maps to ``Memory`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--memory`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

        

        

      command -> (list)

        

        The command that is passed to the container. This parameter maps to ``Cmd`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``COMMAND`` parameter to `docker run <https://docs.docker.com/engine/reference/run/>`_ . For more information, see `https\://docs.docker.com/engine/reference/builder/#cmd <https://docs.docker.com/engine/reference/builder/#cmd>`_ .

        

        (string)

          

          

        

      jobRoleArn -> (string)

        

        The Amazon Resource Name (ARN) of the IAM role that the container can assume for AWS permissions.

        

        

      volumes -> (list)

        

        A list of data volumes used in a job.

        

        (structure)

          

          A data volume used in a job's container properties.

          

          host -> (structure)

            

            The contents of the ``host`` parameter determine whether your data volume persists on the host container instance and where it is stored. If the host parameter is empty, then the Docker daemon assigns a host path for your data volume, but the data is not guaranteed to persist after the containers associated with it stop running.

            

            sourcePath -> (string)

              

              The path on the host container instance that is presented to the container. If this parameter is empty, then the Docker daemon has assigned a host path for you. If the ``host`` parameter contains a ``sourcePath`` file location, then the data volume persists at the specified location on the host container instance until you delete it manually. If the ``sourcePath`` value does not exist on the host container instance, the Docker daemon creates it. If the location does exist, the contents of the source path folder are exported.

              

              

            

          name -> (string)

            

            The name of the volume. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. This name is referenced in the ``sourceVolume`` parameter of container definition ``mountPoints`` .

            

            

          

        

      environment -> (list)

        

        The environment variables to pass to a container. This parameter maps to ``Env`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--env`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

         

        .. warning::

           

          We do not recommend using plain text environment variables for sensitive information, such as credential data.

           

        

        (structure)

          

          A key-value pair object.

          

          name -> (string)

            

            The name of the key value pair. For environment variables, this is the name of the environment variable.

            

            

          value -> (string)

            

            The value of the key value pair. For environment variables, this is the value of the environment variable.

            

            

          

        

      mountPoints -> (list)

        

        The mount points for data volumes in your container. This parameter maps to ``Volumes`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--volume`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

        

        (structure)

          

          Details on a Docker volume mount point that is used in a job's container properties.

          

          containerPath -> (string)

            

            The path on the container at which to mount the host volume.

            

            

          readOnly -> (boolean)

            

            If this value is ``true`` , the container has read-only access to the volume; otherwise, the container can write to the volume. The default value is ``false`` .

            

            

          sourceVolume -> (string)

            

            The name of the volume to mount.

            

            

          

        

      readonlyRootFilesystem -> (boolean)

        

        When this parameter is true, the container is given read-only access to its root file system. This parameter maps to ``ReadonlyRootfs`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--read-only`` option to ``docker run`` .

        

        

      privileged -> (boolean)

        

        When this parameter is true, the container is given elevated privileges on the host container instance (similar to the ``root`` user). This parameter maps to ``Privileged`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--privileged`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

        

        

      ulimits -> (list)

        

        A list of ``ulimits`` to set in the container. This parameter maps to ``Ulimits`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--ulimit`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

        

        (structure)

          

          The ``ulimit`` settings to pass to the container.

          

          hardLimit -> (integer)

            

            The hard limit for the ``ulimit`` type.

            

            

          name -> (string)

            

            The ``type`` of the ``ulimit`` .

            

            

          softLimit -> (integer)

            

            The soft limit for the ``ulimit`` type.

            

            

          

        

      user -> (string)

        

        The user name to use inside the container. This parameter maps to ``User`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--user`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

        

        

      

    

  

nextToken -> (string)

  

  The ``nextToken`` value to include in a future ``describe-job-definitions`` request. When the results of a ``describe-job-definitions`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

