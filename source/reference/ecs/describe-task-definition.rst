[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs describe-task-definition:


************************
describe-task-definition
************************



===========
Description
===========



Describes a task definition. You can specify a ``family`` and ``revision`` to find information about a specific task definition, or you can simply specify the family to find the latest ``ACTIVE`` revision in that family.

 

.. note::

   

  You can only describe ``INACTIVE`` task definitions while an active task or service references them.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecs-2014-11-13/DescribeTaskDefinition>`_


========
Synopsis
========

::

    describe-task-definition
  --task-definition <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--task-definition`` (string)


  The ``family`` for the latest ``ACTIVE`` revision, ``family`` and ``revision`` (``family:revision`` ) for a specific revision in the family, or full Amazon Resource Name (ARN) of the task definition to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a task definition**

This example command provides a description of the specified task definition.

Command::

  aws ecs describe-task-definition --task-definition hello_world:8

Output::

	{
	    "taskDefinition": {
	        "volumes": [],
	        "taskDefinitionArn": "arn:aws:ecs:us-east-1:<aws_account_id>:task-definition/hello_world:8",
	        "containerDefinitions": [
	            {
	                "environment": [],
	                "name": "wordpress",
	                "links": [
	                    "mysql"
	                ],
	                "mountPoints": [],
	                "image": "wordpress",
	                "essential": true,
	                "portMappings": [
	                    {
	                        "containerPort": 80,
	                        "hostPort": 80
	                    }
	                ],
	                "memory": 500,
	                "cpu": 10,
	                "volumesFrom": []
	            },
	            {
	                "environment": [
	                    {
	                        "name": "MYSQL_ROOT_PASSWORD",
	                        "value": "password"
	                    }
	                ],
	                "name": "mysql",
	                "mountPoints": [],
	                "image": "mysql",
	                "cpu": 10,
	                "portMappings": [],
	                "memory": 500,
	                "essential": true,
	                "volumesFrom": []
	            }
	        ],
	        "family": "hello_world",
	        "revision": 8
	    }
	}


======
Output
======

taskDefinition -> (structure)

  

  The full task definition description.

  

  taskDefinitionArn -> (string)

    

    The full Amazon Resource Name (ARN) of the task definition.

    

    

  containerDefinitions -> (list)

    

    A list of container definitions in JSON format that describe the different containers that make up your task. For more information about container definition parameters and defaults, see `Amazon ECS Task Definitions <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_defintions.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

    

    (structure)

      

      Container definitions are used in task definitions to describe the different containers that are launched as part of a task.

      

      name -> (string)

        

        The name of a container. If you are linking multiple containers together in a task definition, the ``name`` of one container can be entered in the ``links`` of another container to connect the containers. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. This parameter maps to ``name`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--name`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ . 

        

        

      image -> (string)

        

        The image used to start a container. This string is passed directly to the Docker daemon. Images in the Docker Hub registry are available by default. Other repositories are specified with `` *repository-url* /*image* :*tag* `` . Up to 255 letters (uppercase and lowercase), numbers, hyphens, underscores, colons, periods, forward slashes, and number signs are allowed. This parameter maps to ``Image`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``IMAGE`` parameter of `docker run <https://docs.docker.com/engine/reference/run/>`_ .

         

         
        * Images in Amazon ECR repositories use the full registry and repository URI (for example, ``012345678910.dkr.ecr.region-name.amazonaws.com/repository-name`` ).  
         
        * Images in official repositories on Docker Hub use a single name (for example, ``ubuntu`` or ``mongo`` ). 
         
        * Images in other repositories on Docker Hub are qualified with an organization name (for example, ``amazon/amazon-ecs-agent`` ). 
         
        * Images in other online repositories are qualified further by a domain name (for example, ``quay.io/assemblyline/ubuntu`` ). 
         

        

        

      cpu -> (integer)

        

        The number of ``cpu`` units reserved for the container. A container instance has 1,024 ``cpu`` units for every CPU core. This parameter specifies the minimum amount of CPU to reserve for a container, and containers share unallocated CPU units with other containers on the instance with the same ratio as their allocated amount. This parameter maps to ``CpuShares`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--cpu-shares`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

         

        .. note::

           

          You can determine the number of CPU units that are available per EC2 instance type by multiplying the vCPUs listed for that instance type on the `Amazon EC2 Instances <http://aws.amazon.com/ec2/instance-types/>`_ detail page by 1,024.

           

         

        For example, if you run a single-container task on a single-core instance type with 512 CPU units specified for that container, and that is the only task running on the container instance, that container could use the full 1,024 CPU unit share at any given time. However, if you launched another copy of the same task on that container instance, each task would be guaranteed a minimum of 512 CPU units when needed, and each container could float to higher CPU usage if the other container was not using it, but if both tasks were 100% active all of the time, they would be limited to 512 CPU units.

         

        The Docker daemon on the container instance uses the CPU value to calculate the relative CPU share ratios for running containers. For more information, see `CPU share constraint <https://docs.docker.com/engine/reference/run/#cpu-share-constraint>`_ in the Docker documentation. The minimum valid CPU share value that the Linux kernel allows is 2; however, the CPU parameter is not required, and you can use CPU values below 2 in your container definitions. For CPU values below 2 (including null), the behavior varies based on your Amazon ECS container agent version:

         

         
        * **Agent versions less than or equal to 1.1.0:** Null and zero CPU values are passed to Docker as 0, which Docker then converts to 1,024 CPU shares. CPU values of 1 are passed to Docker as 1, which the Linux kernel converts to 2 CPU shares. 
         
        * **Agent versions greater than or equal to 1.2.0:** Null, zero, and CPU values of 1 are passed to Docker as 2. 
         

        

        

      memory -> (integer)

        

        The hard limit (in MiB) of memory to present to the container. If your container attempts to exceed the memory specified here, the container is killed. This parameter maps to ``Memory`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--memory`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

         

        You must specify a non-zero integer for one or both of ``memory`` or ``memoryReservation`` in container definitions. If you specify both, ``memory`` must be greater than ``memoryReservation`` . If you specify ``memoryReservation`` , then that value is subtracted from the available memory resources for the container instance on which the container is placed; otherwise, the value of ``memory`` is used.

         

        The Docker daemon reserves a minimum of 4 MiB of memory for a container, so you should not specify fewer than 4 MiB of memory for your containers. 

        

        

      memoryReservation -> (integer)

        

        The soft limit (in MiB) of memory to reserve for the container. When system memory is under heavy contention, Docker attempts to keep the container memory to this soft limit; however, your container can consume more memory when it needs to, up to either the hard limit specified with the ``memory`` parameter (if applicable), or all of the available memory on the container instance, whichever comes first. This parameter maps to ``MemoryReservation`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--memory-reservation`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

         

        You must specify a non-zero integer for one or both of ``memory`` or ``memoryReservation`` in container definitions. If you specify both, ``memory`` must be greater than ``memoryReservation`` . If you specify ``memoryReservation`` , then that value is subtracted from the available memory resources for the container instance on which the container is placed; otherwise, the value of ``memory`` is used.

         

        For example, if your container normally uses 128 MiB of memory, but occasionally bursts to 256 MiB of memory for short periods of time, you can set a ``memoryReservation`` of 128 MiB, and a ``memory`` hard limit of 300 MiB. This configuration would allow the container to only reserve 128 MiB of memory from the remaining resources on the container instance, but also allow the container to consume more memory resources when needed.

        

        

      links -> (list)

        

        The ``link`` parameter allows containers to communicate with each other without the need for port mappings, using the ``name`` parameter and optionally, an ``alias`` for the link. This construct is analogous to ``name:alias`` in Docker links. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed for each ``name`` and ``alias`` . For more information on linking Docker containers, see `https\://docs.docker.com/engine/userguide/networking/default_network/dockerlinks/ <https://docs.docker.com/engine/userguide/networking/default_network/dockerlinks/>`_ . This parameter maps to ``Links`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--link`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

         

        .. warning::

           

          Containers that are collocated on a single container instance may be able to communicate with each other without requiring links or host port mappings. Network isolation is achieved on the container instance using security groups and VPC settings.

           

        

        (string)

          

          

        

      portMappings -> (list)

        

        The list of port mappings for the container. Port mappings allow containers to access ports on the host container instance to send or receive traffic. This parameter maps to ``PortBindings`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--publish`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ . If the network mode of a task definition is set to ``none`` , then you cannot specify port mappings. If the network mode of a task definition is set to ``host`` , then host ports must either be undefined or they must match the container port in the port mapping.

         

        .. note::

           

          After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the **Network Bindings** section of a container description of a selected task in the Amazon ECS console, or the ``networkBindings`` section  describe-tasks responses.

           

        

        (structure)

          

          Port mappings allow containers to access ports on the host container instance to send or receive traffic. Port mappings are specified as part of the container definition. After a task reaches the ``RUNNING`` status, manual and automatic host and container port assignments are visible in the ``networkBindings`` section of  describe-tasks API responses.

          

          containerPort -> (integer)

            

            The port number on the container that is bound to the user-specified or automatically assigned host port. If you specify a container port and not a host port, your container automatically receives a host port in the ephemeral port range (for more information, see ``hostPort`` ). Port mappings that are automatically assigned in this way do not count toward the 100 reserved ports limit of a container instance.

            

            

          hostPort -> (integer)

            

            The port number on the container instance to reserve for your container. You can specify a non-reserved host port for your container port mapping, or you can omit the ``hostPort`` (or set it to ``0`` ) while specifying a ``containerPort`` and your container automatically receives a port in the ephemeral port range for your container instance operating system and Docker version.

             

            The default ephemeral port range for Docker version 1.6.0 and later is listed on the instance under ``/proc/sys/net/ipv4/ip_local_port_range`` ; if this kernel parameter is unavailable, the default ephemeral port range of 49153 to 65535 is used. You should not attempt to specify a host port in the ephemeral port range as these are reserved for automatic assignment. In general, ports below 32768 are outside of the ephemeral port range.

             

            .. note::

               

              The default ephemeral port range of 49153 to 65535 will always be used for Docker versions prior to 1.6.0.

               

             

            The default reserved ports are 22 for SSH, the Docker ports 2375 and 2376, and the Amazon ECS container agent ports 51678 and 51679. Any host port that was previously specified in a running task is also reserved while the task is running (after a task stops, the host port is released).The current reserved ports are displayed in the ``remainingResources`` of  describe-container-instances output, and a container instance may have up to 100 reserved ports at a time, including the default reserved ports (automatically assigned ports do not count toward the 100 reserved ports limit).

            

            

          protocol -> (string)

            

            The protocol used for the port mapping. Valid values are ``tcp`` and ``udp`` . The default is ``tcp`` .

            

            

          

        

      essential -> (boolean)

        

        If the ``essential`` parameter of a container is marked as ``true`` , and that container fails or stops for any reason, all other containers that are part of the task are stopped. If the ``essential`` parameter of a container is marked as ``false`` , then its failure does not affect the rest of the containers in a task. If this parameter is omitted, a container is assumed to be essential.

         

        All tasks must have at least one essential container. If you have an application that is composed of multiple containers, you should group containers that are used for a common purpose into components, and separate the different components into multiple task definitions. For more information, see `Application Architecture <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/application_architecture.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

        

        

      entryPoint -> (list)

        

        .. warning::

           

          Early versions of the Amazon ECS container agent do not properly handle ``entryPoint`` parameters. If you have problems using ``entryPoint`` , update your container agent or enter your commands and arguments as ``command`` array items instead.

           

         

        The entry point that is passed to the container. This parameter maps to ``Entrypoint`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--entrypoint`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ . For more information, see `https\://docs.docker.com/engine/reference/builder/#entrypoint <https://docs.docker.com/engine/reference/builder/#entrypoint>`_ .

        

        (string)

          

          

        

      command -> (list)

        

        The command that is passed to the container. This parameter maps to ``Cmd`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``COMMAND`` parameter to `docker run <https://docs.docker.com/engine/reference/run/>`_ . For more information, see `https\://docs.docker.com/engine/reference/builder/#cmd <https://docs.docker.com/engine/reference/builder/#cmd>`_ .

        

        (string)

          

          

        

      environment -> (list)

        

        The environment variables to pass to a container. This parameter maps to ``Env`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--env`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

         

        .. warning::

           

          We do not recommend using plain text environment variables for sensitive information, such as credential data.

           

        

        (structure)

          

          A key and value pair object.

          

          name -> (string)

            

            The name of the key value pair. For environment variables, this is the name of the environment variable.

            

            

          value -> (string)

            

            The value of the key value pair. For environment variables, this is the value of the environment variable.

            

            

          

        

      mountPoints -> (list)

        

        The mount points for data volumes in your container. This parameter maps to ``Volumes`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--volume`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

        

        (structure)

          

          Details on a volume mount point that is used in a container definition.

          

          sourceVolume -> (string)

            

            The name of the volume to mount.

            

            

          containerPath -> (string)

            

            The path on the container to mount the host volume at.

            

            

          readOnly -> (boolean)

            

            If this value is ``true`` , the container has read-only access to the volume. If this value is ``false`` , then the container can write to the volume. The default value is ``false`` .

            

            

          

        

      volumesFrom -> (list)

        

        Data volumes to mount from another container. This parameter maps to ``VolumesFrom`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--volumes-from`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

        

        (structure)

          

          Details on a data volume from another container in the same task definition.

          

          sourceContainer -> (string)

            

            The name of another container within the same task definition to mount volumes from.

            

            

          readOnly -> (boolean)

            

            If this value is ``true`` , the container has read-only access to the volume. If this value is ``false`` , then the container can write to the volume. The default value is ``false`` .

            

            

          

        

      hostname -> (string)

        

        The hostname to use for your container. This parameter maps to ``Hostname`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--hostname`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

        

        

      user -> (string)

        

        The user name to use inside the container. This parameter maps to ``User`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--user`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

        

        

      workingDirectory -> (string)

        

        The working directory in which to run commands inside the container. This parameter maps to ``WorkingDir`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--workdir`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

        

        

      disableNetworking -> (boolean)

        

        When this parameter is true, networking is disabled within the container. This parameter maps to ``NetworkDisabled`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ .

        

        

      privileged -> (boolean)

        

        When this parameter is true, the container is given elevated privileges on the host container instance (similar to the ``root`` user). This parameter maps to ``Privileged`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--privileged`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

        

        

      readonlyRootFilesystem -> (boolean)

        

        When this parameter is true, the container is given read-only access to its root file system. This parameter maps to ``ReadonlyRootfs`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--read-only`` option to ``docker run`` .

        

        

      dnsServers -> (list)

        

        A list of DNS servers that are presented to the container. This parameter maps to ``Dns`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--dns`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

        

        (string)

          

          

        

      dnsSearchDomains -> (list)

        

        A list of DNS search domains that are presented to the container. This parameter maps to ``DnsSearch`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--dns-search`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

        

        (string)

          

          

        

      extraHosts -> (list)

        

        A list of hostnames and IP address mappings to append to the ``/etc/hosts`` file on the container. This parameter maps to ``ExtraHosts`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--add-host`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

        

        (structure)

          

          Hostnames and IP address entries that are added to the ``/etc/hosts`` file of a container via the ``extraHosts`` parameter of its  ContainerDefinition . 

          

          hostname -> (string)

            

            The hostname to use in the ``/etc/hosts`` entry.

            

            

          ipAddress -> (string)

            

            The IP address to use in the ``/etc/hosts`` entry.

            

            

          

        

      dockerSecurityOptions -> (list)

        

        A list of strings to provide custom labels for SELinux and AppArmor multi-level security systems. This parameter maps to ``SecurityOpt`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--security-opt`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ .

         

        .. note::

           

          The Amazon ECS container agent running on a container instance must register with the ``ECS_SELINUX_CAPABLE=true`` or ``ECS_APPARMOR_CAPABLE=true`` environment variables before containers placed on that instance can use these security options. For more information, see `Amazon ECS Container Agent Configuration <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-agent-config.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

           

        

        (string)

          

          

        

      dockerLabels -> (map)

        

        A key/value map of labels to add to the container. This parameter maps to ``Labels`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--label`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ . This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      ulimits -> (list)

        

        A list of ``ulimits`` to set in the container. This parameter maps to ``Ulimits`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--ulimit`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ . Valid naming values are displayed in the  Ulimit data type. This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

        

        (structure)

          

          The ``ulimit`` settings to pass to the container.

          

          name -> (string)

            

            The ``type`` of the ``ulimit`` .

            

            

          softLimit -> (integer)

            

            The soft limit for the ulimit type.

            

            

          hardLimit -> (integer)

            

            The hard limit for the ulimit type.

            

            

          

        

      logConfiguration -> (structure)

        

        The log configuration specification for the container. This parameter maps to ``LogConfig`` in the `Create a container <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/#create-a-container>`_ section of the `Docker Remote API <https://docs.docker.com/engine/reference/api/docker_remote_api_v1.23/>`_ and the ``--log-driver`` option to `docker run <https://docs.docker.com/engine/reference/run/>`_ . By default, containers use the same logging driver that the Docker daemon uses; however the container may use a different logging driver than the Docker daemon by specifying a log driver with this parameter in the container definition. To use a different logging driver for a container, the log system must be configured properly on the container instance (or on a different log server for remote logging options). For more information on the options for different supported log drivers, see `Configure logging drivers <https://docs.docker.com/engine/admin/logging/overview/>`_ in the Docker documentation.

         

        .. note::

           

          Amazon ECS currently supports a subset of the logging drivers available to the Docker daemon (shown in the  LogConfiguration data type). Additional log drivers may be available in future releases of the Amazon ECS container agent.

           

         

        This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

         

        .. note::

           

          The Amazon ECS container agent running on a container instance must register the logging drivers available on that instance with the ``ECS_AVAILABLE_LOGGING_DRIVERS`` environment variable before containers placed on that instance can use these log configuration options. For more information, see `Amazon ECS Container Agent Configuration <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-agent-config.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

           

        

        logDriver -> (string)

          

          The log driver to use for the container. The valid values listed for this parameter are log drivers that the Amazon ECS container agent can communicate with by default. 

           

          .. note::

             

            If you have a custom driver that is not listed above that you would like to work with the Amazon ECS container agent, you can fork the Amazon ECS container agent project that is `available on GitHub <https://github.com/aws/amazon-ecs-agent>`_ and customize it to work with that driver. We encourage you to submit pull requests for changes that you would like to have included. However, Amazon Web Services does not currently provide support for running modified copies of this software.

             

           

          This parameter requires version 1.18 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

          

          

        options -> (map)

          

          The configuration options to send to the log driver. This parameter requires version 1.19 of the Docker Remote API or greater on your container instance. To check the Docker Remote API version on your container instance, log into your container instance and run the following command: ``sudo docker version | grep "Server API version"``  

          

          key -> (string)

            

            

          value -> (string)

            

            

          

        

      

    

  family -> (string)

    

    The family of your task definition, used as the definition name.

    

    

  taskRoleArn -> (string)

    

    The Amazon Resource Name (ARN) of the IAM role that containers in this task can assume. All containers in this task are granted the permissions that are specified in this role.

    

    

  networkMode -> (string)

    

    The Docker networking mode to use for the containers in the task. The valid values are ``none`` , ``bridge`` , and ``host`` . 

     

    If the network mode is ``none`` , the containers do not have external connectivity. The default Docker network mode is ``bridge`` . The ``host`` network mode offers the highest networking performance for containers because it uses the host network stack instead of the virtualized network stack provided by the ``bridge`` mode.

     

    For more information, see `Network settings <https://docs.docker.com/engine/reference/run/#network-settings>`_ in the *Docker run reference* .

    

    

  revision -> (integer)

    

    The revision of the task in a particular family. The revision is a version number of a task definition in a family. When you register a task definition for the first time, the revision is ``1`` ; each time you register a new revision of a task definition in the same family, the revision value always increases by one (even if you have deregistered previous revisions in this family).

    

    

  volumes -> (list)

    

    The list of volumes in a task. For more information about volume definition parameters and defaults, see `Amazon ECS Task Definitions <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_defintions.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

    

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

      

      An attribute is a name-value pair associated with an Amazon ECS object. Attributes enable you to extend the Amazon ECS data model by adding custom metadata to your resources. For more information, see `Attributes <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-placement-constraints.html#attributes>`_ in the *Amazon EC2 Container Service Developer Guide* .

      

      name -> (string)

        

        The name of the attribute. Up to 128 letters (uppercase and lowercase), numbers, hyphens, underscores, and periods are allowed.

        

        

      value -> (string)

        

        The value of the attribute. Up to 128 letters (uppercase and lowercase), numbers, hyphens, underscores, periods, at signs (@), forward slashes, colons, and spaces are allowed.

        

        

      targetType -> (string)

        

        The type of the target with which to attach the attribute. This parameter is required if you use the short form ID for a resource instead of the full Amazon Resource Name (ARN).

        

        

      targetId -> (string)

        

        The ID of the target. You can specify the short form ID for a resource or the full Amazon Resource Name (ARN).

        

        

      

    

  placementConstraints -> (list)

    

    An array of placement constraint objects to use for tasks. 

    

    (structure)

      

      An object representing a constraint on task placement in the task definition. For more information, see `Task Placement Constraints <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-placement-constraints.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

      

      type -> (string)

        

        The type of constraint. The ``DistinctInstance`` constraint ensures that each task in a particular group is running on a different container instance. The ``MemberOf`` constraint restricts selection to be from a group of valid candidates.

        

        

      expression -> (string)

        

        A cluster query language expression to apply to the constraint. For more information, see `Cluster Query Language <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/cluster-query-language.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

        

        

      

    

  

