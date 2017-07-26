[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs deregister-task-definition:


**************************
deregister-task-definition
**************************



===========
Description
===========



Deregisters the specified task definition by family and revision. Upon deregistration, the task definition is marked as ``INACTIVE`` . Existing tasks and services that reference an ``INACTIVE`` task definition continue to run without disruption. Existing services that reference an ``INACTIVE`` task definition can still scale up or down by modifying the service's desired count.

 

You cannot use an ``INACTIVE`` task definition to run new tasks or create new services, and you cannot update an existing service to reference an ``INACTIVE`` task definition (although there may be up to a 10 minute window following deregistration where these restrictions have not yet taken effect).



========
Synopsis
========

::

    deregister-task-definition
  --task-definition <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--task-definition`` (string)


  The ``family`` and ``revision`` (``family:revision`` ) or full Amazon Resource Name (ARN) of the task definition to deregister. You must specify a ``revision`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To deregister a task definition**

This example deregisters the first revision of the ``curler`` task definition in your default region. Note that in the resulting output, the task definition status becomes ``INACTIVE``.

Command::

  aws ecs deregister-task-definition --task-definition curler:1

Output::

  {
      "taskDefinition": {
          "status": "INACTIVE",
          "family": "curler",
          "volumes": [],
          "taskDefinitionArn": "arn:aws:ecs:us-west-2:<aws_account_id>:task-definition/curler:1",
          "containerDefinitions": [
              {
                  "environment": [],
                  "name": "curler",
                  "mountPoints": [],
                  "image": "curl:latest",
                  "cpu": 100,
                  "portMappings": [],
                  "entryPoint": [],
                  "memory": 256,
                  "command": [
                      "curl -v http://example.com/"
                  ],
                  "essential": true,
                  "volumesFrom": []
              }
          ],
          "revision": 1
      }
  }

======
Output
======

taskDefinition -> (structure)

  

  The full description of the deregistered task.

  

  taskDefinitionArn -> (string)

    

    The full Amazon Resource Name (ARN) of the of the task definition.

    

    

  containerDefinitions -> (list)

    

    A list of container definitions in JSON format that describe the different containers that make up your task. For more information about container definition parameters and defaults, see `Amazon ECS Task Definitions`_ in the *Amazon EC2 Container Service Developer Guide* .

    

    (structure)

      

      Container definitions are used in task definitions to describe the different containers that are launched as part of a task.

      

      name -> (string)

        

        The name of a container. If you are linking multiple containers together in a task definition, the ``name`` of one container can be entered in the ``links`` of another container to connect the containers. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. This parameter maps to ``name`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--name`` option to `docker run`_ . 

        

        

      image -> (string)

        

        The image used to start a container. This string is passed directly to the Docker daemon. Images in the Docker Hub registry are available by default. Other repositories are specified with ``*repository-url* /*image* :*tag*`` . Up to 255 letters (uppercase and lowercase), numbers, hyphens, underscores, colons, periods, forward slashes, and number signs are allowed. This parameter maps to ``Image`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``IMAGE`` parameter of `docker run`_ .

         

         
        * Images in official repositories on Docker Hub use a single name (for example, ``ubuntu`` or ``mongo`` ).
         
        * Images in other repositories on Docker Hub are qualified with an organization name (for example, ``amazon/amazon-ecs-agent`` ).
         
        * Images in other online repositories are qualified further by a domain name (for example, ``quay.io/assemblyline/ubuntu`` ).
         

        

        

      cpu -> (integer)

        

        The number of ``cpu`` units reserved for the container. A container instance has 1,024 ``cpu`` units for every CPU core. This parameter specifies the minimum amount of CPU to reserve for a container, and containers share unallocated CPU units with other containers on the instance with the same ratio as their allocated amount. This parameter maps to ``CpuShares`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--cpu-shares`` option to `docker run`_ .

         

        .. note::

           

          You can determine the number of CPU units that are available per EC2 instance type by multiplying the vCPUs listed for that instance type on the `Amazon EC2 Instances`_ detail page by 1,024.

           

         

        For example, if you run a single-container task on a single-core instance type with 512 CPU units specified for that container, and that is the only task running on the container instance, that container could use the full 1,024 CPU unit share at any given time. However, if you launched another copy of the same task on that container instance, each task would be guaranteed a minimum of 512 CPU units when needed, and each container could float to higher CPU usage if the other container was not using it, but if both tasks were 100% active all of the time, they would be limited to 512 CPU units.

         

        The Docker daemon on the container instance uses the CPU value to calculate the relative CPU share ratios for running containers. For more information, see `CPU share constraint`_ in the Docker documentation. The minimum valid CPU share value that the Linux kernel allows is 2; however, the CPU parameter is not required, and you can use CPU values below 2 in your container definitions. For CPU values below 2 (including null), the behavior varies based on your Amazon ECS container agent version:

         

         
        * **Agent versions less than or equal to 1.1.0:** Null and zero CPU values are passed to Docker as 0, which Docker then converts to 1,024 CPU shares. CPU values of 1 are passed to Docker as 1, which the Linux kernel converts to 2 CPU shares.
         
        * **Agent versions greater than or equal to 1.2.0:** Null, zero, and CPU values of 1 are passed to Docker as 2.
        

        

        

      memory -> (integer)

        

        The number of MiB of memory to reserve for the container. You must specify a non-zero integer for this parameter; the Docker daemon reserves a minimum of 4 MiB of memory for a container, so you should not specify fewer than 4 MiB of memory for your containers. If your container attempts to exceed the memory allocated here, the container is killed. This parameter maps to ``Memory`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--memory`` option to `docker run`_ .

        

        

      links -> (list)

        

        The ``link`` parameter allows containers to communicate with each other without the need for port mappings, using the ``name`` parameter and optionally, an ``alias`` for the link. This construct is analogous to ``name:alias`` in Docker links. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed for each ``name`` and ``alias`` . For more information on linking Docker containers, see `https\://docs.docker.com/userguide/dockerlinks/`_ . This parameter maps to ``Links`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--link`` option to ```docker run```_ .

         

        .. warning::

           

          Containers that are collocated on a single container instance may be able to communicate with each other without requiring links or host port mappings. Network isolation is achieved on the container instance using security groups and VPC settings.

           

        

        (string)

          

          

        

      portMappings -> (list)

        

        The list of port mappings for the container. Port mappings allow containers to access ports on the host container instance to send or receive traffic. This parameter maps to ``PortBindings`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--publish`` option to `docker run`_ .

         

        .. note::

           

          After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the **Network Bindings** section of a container description of a selected task in the Amazon ECS console, or the ``networkBindings`` section  describe-tasks responses.

           

        

        (structure)

          

          Port mappings allow containers to access ports on the host container instance to send or receive traffic. Port mappings are specified as part of the container definition. After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the ``networkBindings`` section of  describe-tasks API responses.

          

          containerPort -> (integer)

            

            The port number on the container that is bound to the user-specified or automatically assigned host port. If you specify a container port and not a host port, your container automatically receives a host port in the ephemeral port range (for more information, see ``hostPort`` ).

            

            

          hostPort -> (integer)

            

            The port number on the container instance to reserve for your container. You can specify a non-reserved host port for your container port mapping, or you can omit the ``hostPort`` (or set it to ``0`` ) while specifying a ``containerPort`` and your container automatically receives a port in the ephemeral port range for your container instance operating system and Docker version.

             

            The default ephemeral port range is 49153 to 65535, and this range is used for Docker versions prior to 1.6.0. For Docker version 1.6.0 and later, the Docker daemon tries to read the ephemeral port range from ``/proc/sys/net/ipv4/ip_local_port_range`` ; if this kernel parameter is unavailable, the default ephemeral port range is used. You should not attempt to specify a host port in the ephemeral port range, because these are reserved for automatic assignment. In general, ports below 32768 are outside of the ephemeral port range.

             

            The default reserved ports are 22 for SSH, the Docker ports 2375 and 2376, and the Amazon ECS container agent port 51678. Any host port that was previously specified in a running task is also reserved while the task is running (after a task stops, the host port is released).The current reserved ports are displayed in the ``remainingResources`` of  describe-container-instances output, and a container instance may have up to 50 reserved ports at a time, including the default reserved ports (automatically assigned ports do not count toward this limit).

            

            

          protocol -> (string)

            

            The protocol used for the port mapping. Valid values are ``tcp`` and ``udp`` . The default is ``tcp`` .

            

            

          

        

      essential -> (boolean)

        

        If the ``essential`` parameter of a container is marked as ``true`` , the failure of that container stops the task. If the ``essential`` parameter of a container is marked as ``false`` , then its failure does not affect the rest of the containers in a task. If this parameter is omitted, a container is assumed to be essential.

         

        .. note::

           

          All tasks must have at least one essential container.

           

        

        

      entryPoint -> (list)

        

        .. warning::

           

          Early versions of the Amazon ECS container agent do not properly handle ``entryPoint`` parameters. If you have problems using ``entryPoint`` , update your container agent or enter your commands and arguments as ``command`` array items instead.

           

         

        The entry point that is passed to the container. This parameter maps to ``Entrypoint`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--entrypoint`` option to `docker run`_ . For more information, see `https\://docs.docker.com/reference/builder/#entrypoint`_ .

        

        (string)

          

          

        

      command -> (list)

        

        The command that is passed to the container. This parameter maps to ``Cmd`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``COMMAND`` parameter to `docker run`_ . For more information, see `https\://docs.docker.com/reference/builder/#cmd`_ .

        

        (string)

          

          

        

      environment -> (list)

        

        The environment variables to pass to a container. This parameter maps to ``Env`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--env`` option to `docker run`_ .

         

        .. warning::

           

          We do not recommend using plain text environment variables for sensitive information, such as credential data.

           

        

        (structure)

          

          A key and value pair object.

          

          name -> (string)

            

            The name of the key value pair. For environment variables, this is the name of the environment variable.

            

            

          value -> (string)

            

            The value of the key value pair. For environment variables, this is the value of the environment variable.

            

            

          

        

      mountPoints -> (list)

        

        The mount points for data volumes in your container. This parameter maps to ``Volumes`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--volume`` option to `docker run`_ .

        

        (structure)

          

          Details on a volume mount point that is used in a container definition.

          

          sourceVolume -> (string)

            

            The name of the volume to mount.

            

            

          containerPath -> (string)

            

            The path on the container to mount the host volume at.

            

            

          readOnly -> (boolean)

            

            If this value is ``true`` , the container has read-only access to the volume. If this value is ``false`` , then the container can write to the volume. The default value is ``false`` .

            

            

          

        

      volumesFrom -> (list)

        

        Data volumes to mount from another container. This parameter maps to ``VolumesFrom`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--volumes-from`` option to `docker run`_ .

        

        (structure)

          

          Details on a data volume from another container.

          

          sourceContainer -> (string)

            

            The name of the container to mount volumes from.

            

            

          readOnly -> (boolean)

            

            If this value is ``true`` , the container has read-only access to the volume. If this value is ``false`` , then the container can write to the volume. The default value is ``false`` .

            

            

          

        

      hostname -> (string)

        

        The hostname to use for your container. This parameter maps to ``Hostname`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--hostname`` option to `docker run`_ .

        

        

      user -> (string)

        

        The user name to use inside the container. This parameter maps to ``User`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--user`` option to `docker run`_ .

        

        

      workingDirectory -> (string)

        

        The working directory in which to run commands inside the container. This parameter maps to ``WorkingDir`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--workdir`` option to `docker run`_ .

        

        

      disableNetworking -> (boolean)

        

        When this parameter is true, networking is disabled within the container. This parameter maps to ``NetworkDisabled`` in the `Create a container`_ section of the `Docker Remote API`_ .

        

        

      privileged -> (boolean)

        

        When this parameter is true, the container is given elevated privileges on the host container instance (similar to the ``root`` user). This parameter maps to ``Privileged`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--privileged`` option to `docker run`_ .

        

        

      readonlyRootFilesystem -> (boolean)

        

        When this parameter is true, the container is given read-only access to its root file system. This parameter maps to ``ReadonlyRootfs`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--read-only`` option to ``docker run`` .

        

        

      dnsServers -> (list)

        

        A list of DNS servers that are presented to the container. This parameter maps to ``Dns`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--dns`` option to `docker run`_ .

        

        (string)

          

          

        

      dnsSearchDomains -> (list)

        

        A list of DNS search domains that are presented to the container. This parameter maps to ``DnsSearch`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--dns-search`` option to `docker run`_ .

        

        (string)

          

          

        

      extraHosts -> (list)

        

        A list of hostnames and IP address mappings to append to the ``/etc/hosts`` file on the container. This parameter maps to ``ExtraHosts`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--add-host`` option to `docker run`_ .

        

        (structure)

          

          Hostnames and IP address entries that are added to the ``/etc/hosts`` file of a container via the ``extraHosts`` parameter of its  ContainerDefinition . 

          

          hostname -> (string)

            

            The hostname to use in the ``/etc/hosts`` entry.

            

            

          ipAddress -> (string)

            

            The IP address to use in the ``/etc/hosts`` entry.

            

            

          

        

      dockerSecurityOptions -> (list)

        

        A list of strings to provide custom labels for SELinux and AppArmor multi-level security systems. This parameter maps to ``SecurityOpt`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--security-opt`` option to `docker run`_ .

         

        .. note::

           

          The Amazon ECS container agent running on a container instance must register with the ``ECS_SELINUX_CAPABLE=true`` or ``ECS_APPARMOR_CAPABLE=true`` environment variables before containers placed on that instance can use these security options. For more information, see `Amazon ECS Container Agent Configuration`_ in the *Amazon EC2 Container Service Developer Guide* .

           

        

        (string)

          

          

        

      dockerLabels -> (map)

        

        A key/value map of labels to add to the container. This parameter maps to ``Labels`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--label`` option to `docker run`_ . This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      ulimits -> (list)

        

        A list of ``ulimits`` to set in the container. This parameter maps to ``Ulimits`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--ulimit`` option to `docker run`_ . Valid naming values are displayed in the  Ulimit data type. This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"`` 

        

        (structure)

          

          The ``ulimit`` settings to pass to the container.

          

          name -> (string)

            

            The ``type`` of the ``ulimit`` .

            

            

          softLimit -> (integer)

            

            The soft limit for the ulimit type.

            

            

          hardLimit -> (integer)

            

            The hard limit for the ulimit type.

            

            

          

        

      logConfiguration -> (structure)

        

        The log configuration specification for the container. This parameter maps to ``LogConfig`` in the `Create a container`_ section of the `Docker Remote API`_ and the ``--log-driver`` option to `docker run`_ . Valid log drivers are displayed in the  LogConfiguration data type. This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"`` 

         

        .. note::

           

          The Amazon ECS container agent running on a container instance must register the logging drivers available on that instance with the ``ECS_AVAILABLE_LOGGING_DRIVERS`` environment variable before containers placed on that instance can use these log configuration options. For more information, see `Amazon ECS Container Agent Configuration`_ in the *Amazon EC2 Container Service Developer Guide* .

           

        

        logDriver -> (string)

          

          The log driver to use for the container. This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"`` 

          

          

        options -> (map)

          

          The configuration options to send to the log driver. This parameter requires version 1.19 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"`` 

          

          key -> (string)

            

            

          value -> (string)

            

            

          

        

      

    

  family -> (string)

    

    The family of your task definition, used as the definition name.

    

    

  revision -> (integer)

    

    The revision of the task in a particular family. The revision is a version number of a task definition in a family. When you register a task definition for the first time, the revision is ``1`` ; each time you register a new revision of a task definition in the same family, the revision value always increases by one (even if you have deregistered previous revisions in this family).

    

    

  volumes -> (list)

    

    The list of volumes in a task. For more information about volume definition parameters and defaults, see `Amazon ECS Task Definitions`_ in the *Amazon EC2 Container Service Developer Guide* .

    

    (structure)

      

      A data volume used in a task definition.

      

      name -> (string)

        

        The name of the volume. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. This name is referenced in the ``sourceVolume`` parameter of container definition ``mountPoints`` .

        

        

      host -> (structure)

        

        The contents of the ``host`` parameter determine whether your data volume persists on the host container instance and where it is stored. If the host parameter is empty, then the Docker daemon assigns a host path for your data volume, but the data is not guaranteed to persist after the containers associated with it stop running.

        

        sourcePath -> (string)

          

          The path on the host container instance that is presented to the container. If this parameter is empty, then the Docker daemon has assigned a host path for you. If the ``host`` parameter contains a ``sourcePath`` file location, then the data volume persists at the specified location on the host container instance until you delete it manually. If the ``sourcePath`` value does not exist on the host container instance, the Docker daemon creates it. If the location does exist, the contents of the source path folder are exported.

          

          

        

      

    

  status -> (string)

    

    The status of the task definition.

    

    

  requiresAttributes -> (list)

    

    The container instance attributes required by your task.

    

    (structure)

      

      The attributes applicable to a container instance when it is registered.

      

      name -> (string)

        

        The name of the container instance attribute.

        

        

      value -> (string)

        

        The value of the container instance attribute (at this time, the value here is ``Null`` , but this could change in future revisions for expandability).

        

        

      

    

  



.. _``: https://docs.docker.com/reference/commandline/run/
.. _https\://docs.docker.com/userguide/dockerlinks/: https://docs.docker.com/userguide/dockerlinks/
.. _CPU share constraint: https://docs.docker.com/reference/run/#cpu-share-constraint
.. _Amazon ECS Container Agent Configuration: http://docs.aws.amazon.com/AmazonECS/latest/developerguide/developerguide/ecs-agent-config.html
.. _https\://docs.docker.com/reference/builder/#cmd: https://docs.docker.com/reference/builder/#cmd
.. _https\://docs.docker.com/reference/builder/#entrypoint: https://docs.docker.com/reference/builder/#entrypoint
.. _docker run: https://docs.docker.com/reference/commandline/run/
.. _Create a container: https://docs.docker.com/reference/api/docker_remote_api_v1.19/#create-a-container
.. _Amazon ECS Task Definitions: http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_defintions.html
.. _Amazon EC2 Instances: http://aws.amazon.com/ec2/instance-types/
.. _Docker Remote API: https://docs.docker.com/reference/api/docker_remote_api_v1.19/
