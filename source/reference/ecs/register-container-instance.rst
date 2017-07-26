[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs register-container-instance:


***************************
register-container-instance
***************************



===========
Description
===========



.. note::

  

  This action is only used by the Amazon EC2 Container Service agent, and it is not intended for use outside of the agent.

  

 

Registers an EC2 instance into the specified cluster. This instance becomes available to place containers on.



========
Synopsis
========

::

    register-container-instance
  [--cluster <value>]
  [--instance-identity-document <value>]
  [--instance-identity-document-signature <value>]
  [--total-resources <value>]
  [--version-info <value>]
  [--container-instance-arn <value>]
  [--attributes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster with which to register your container instance. If you do not specify a cluster, the default cluster is assumed..

  

``--instance-identity-document`` (string)


  The instance identity document for the EC2 instance to register. This document can be found by running the following command from the instance: ``curl http://169.254.169.254/latest/dynamic/instance-identity/document/`` 

  

``--instance-identity-document-signature`` (string)


  The instance identity document signature for the EC2 instance to register. This signature can be found by running the following command from the instance: ``curl http://169.254.169.254/latest/dynamic/instance-identity/signature/`` 

  

``--total-resources`` (list)


  The resources available on the instance.

  



Shorthand Syntax::

    name=string,type=string,doubleValue=double,longValue=long,integerValue=integer,stringSetValue=string,string ...




JSON Syntax::

  [
    {
      "name": "string",
      "type": "string",
      "doubleValue": double,
      "longValue": long,
      "integerValue": integer,
      "stringSetValue": ["string", ...]
    }
    ...
  ]



``--version-info`` (structure)


  The version information for the Amazon ECS container agent and Docker daemon running on the container instance.

  



Shorthand Syntax::

    agentVersion=string,agentHash=string,dockerVersion=string




JSON Syntax::

  {
    "agentVersion": "string",
    "agentHash": "string",
    "dockerVersion": "string"
  }



``--container-instance-arn`` (string)


  The Amazon Resource Name (ARN) of the container instance (if it was previously registered).

  

``--attributes`` (list)


  The container instance attributes that this container instance supports.

  



Shorthand Syntax::

    name=string,value=string ...




JSON Syntax::

  [
    {
      "name": "string",
      "value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

containerInstance -> (structure)

  

  An EC2 instance that is running the Amazon ECS agent and has been registered with a cluster.

  

  containerInstanceArn -> (string)

    

    The Amazon Resource Name (ARN) of the container instance. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the container instance, the AWS account ID of the container instance owner, the ``container-instance`` namespace, and then the container instance ID. For example, arn:aws:ecs:*region* :*aws_account_id* :container-instance/*container_instance_ID* .

    

    

  ec2InstanceId -> (string)

    

    The EC2 instance ID of the container instance.

    

    

  versionInfo -> (structure)

    

    The version information for the Amazon ECS container agent and Docker daemon running on the container instance.

    

    agentVersion -> (string)

      

      The version number of the Amazon ECS container agent.

      

      

    agentHash -> (string)

      

      The Git commit hash for the Amazon ECS container agent build on the `amazon-ecs-agent`_ GitHub repository.

      

      

    dockerVersion -> (string)

      

      The Docker version running on the container instance.

      

      

    

  remainingResources -> (list)

    

    The remaining resources of the container instance that are available for new tasks.

    

    (structure)

      

      Describes the resources available for a container instance.

      

      name -> (string)

        

        The name of the resource, such as ``CPU`` , ``MEMORY`` , ``PORTS`` , or a user-defined resource.

        

        

      type -> (string)

        

        The type of the resource, such as ``INTEGER`` , ``DOUBLE`` , ``LONG`` , or ``STRINGSET`` .

        

        

      doubleValue -> (double)

        

        When the ``doubleValue`` type is set, the value of the resource must be a double precision floating-point type.

        

        

      longValue -> (long)

        

        When the ``longValue`` type is set, the value of the resource must be an extended precision floating-point type.

        

        

      integerValue -> (integer)

        

        When the ``integerValue`` type is set, the value of the resource must be an integer.

        

        

      stringSetValue -> (list)

        

        When the ``stringSetValue`` type is set, the value of the resource must be a string type.

        

        (string)

          

          

        

      

    

  registeredResources -> (list)

    

    The registered resources on the container instance that are in use by current tasks.

    

    (structure)

      

      Describes the resources available for a container instance.

      

      name -> (string)

        

        The name of the resource, such as ``CPU`` , ``MEMORY`` , ``PORTS`` , or a user-defined resource.

        

        

      type -> (string)

        

        The type of the resource, such as ``INTEGER`` , ``DOUBLE`` , ``LONG`` , or ``STRINGSET`` .

        

        

      doubleValue -> (double)

        

        When the ``doubleValue`` type is set, the value of the resource must be a double precision floating-point type.

        

        

      longValue -> (long)

        

        When the ``longValue`` type is set, the value of the resource must be an extended precision floating-point type.

        

        

      integerValue -> (integer)

        

        When the ``integerValue`` type is set, the value of the resource must be an integer.

        

        

      stringSetValue -> (list)

        

        When the ``stringSetValue`` type is set, the value of the resource must be a string type.

        

        (string)

          

          

        

      

    

  status -> (string)

    

    The status of the container instance. The valid values are ``ACTIVE`` or ``INACTIVE`` . ``ACTIVE`` indicates that the container instance can accept tasks.

    

    

  agentConnected -> (boolean)

    

    This parameter returns ``true`` if the agent is actually connected to Amazon ECS. Registered instances with an agent that may be unhealthy or stopped return ``false`` , and instances without a connected agent cannot accept placement requests.

    

    

  runningTasksCount -> (integer)

    

    The number of tasks on the container instance that are in the ``RUNNING`` status.

    

    

  pendingTasksCount -> (integer)

    

    The number of tasks on the container instance that are in the ``PENDING`` status.

    

    

  agentUpdateStatus -> (string)

    

    The status of the most recent agent update. If an update has never been requested, this value is ``NULL`` .

    

    

  attributes -> (list)

    

    The attributes set for the container instance by the Amazon ECS container agent at instance registration.

    

    (structure)

      

      The attributes applicable to a container instance when it is registered.

      

      name -> (string)

        

        The name of the container instance attribute.

        

        

      value -> (string)

        

        The value of the container instance attribute (at this time, the value here is ``Null`` , but this could change in future revisions for expandability).

        

        

      

    

  



.. _amazon-ecs-agent: https://github.com/aws/amazon-ecs-agent/commits/master
