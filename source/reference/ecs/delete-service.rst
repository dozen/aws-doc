[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs delete-service:


**************
delete-service
**************



===========
Description
===========



Deletes a specified service within a cluster. You can delete a service if you have no running tasks in it and the desired task count is zero. If the service is actively maintaining tasks, you cannot delete it, and you must update the service to a desired task count of zero. For more information, see  update-service .

 

.. note::

   

  When you delete a service, if there are still running tasks that require cleanup, the service status moves from ``ACTIVE`` to ``DRAINING`` , and the service is no longer visible in the console or in  list-services API operations. After the tasks have stopped, then the service status moves from ``DRAINING`` to ``INACTIVE`` . Services in the ``DRAINING`` or ``INACTIVE`` status can still be viewed with  describe-services API operations; however, in the future, ``INACTIVE`` services may be cleaned up and purged from Amazon ECS record keeping, and  describe-services API operations on those services will return a ``ServiceNotFoundException`` error.

   



========
Synopsis
========

::

    delete-service
  [--cluster <value>]
  --service <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster`` (string)


  The name of the cluster that hosts the service to delete. If you do not specify a cluster, the default cluster is assumed.

  

``--service`` (string)


  The name of the service to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a service**

This example command deletes the ``my-http-service`` service. The service must have a desired count and running count of 0 before you can delete it.

Command::

  aws ecs delete-service --service my-http-service



======
Output
======

service -> (structure)

  

  The full description of the deleted service.

  

  serviceArn -> (string)

    

    The Amazon Resource Name (ARN) that identifies the service. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the service, the AWS account ID of the service owner, the ``service`` namespace, and then the service name. For example, arn:aws:ecs:*region* :*012345678910* :service/*my-service* .

    

    

  serviceName -> (string)

    

    The name of your service. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. Service names must be unique within a cluster, but you can have similarly named services in multiple clusters within a region or across multiple regions.

    

    

  clusterArn -> (string)

    

    The Amazon Resource Name (ARN) of the of the cluster that hosts the service.

    

    

  loadBalancers -> (list)

    

    A list of load balancer objects, containing the load balancer name, the container name (as it appears in a container definition), and the container port to access from the load balancer.

    

    (structure)

      

      Details on a load balancer that is used with a service.

      

      loadBalancerName -> (string)

        

        The name of the load balancer.

        

        

      containerName -> (string)

        

        The name of the container (as it appears in a container definition) to associate with the load balancer.

        

        

      containerPort -> (integer)

        

        The port on the container to associate with the load balancer. This port must correspond to a ``containerPort`` in the service's task definition. Your container instances must allow ingress traffic on the ``hostPort`` of the port mapping.

        

        

      

    

  status -> (string)

    

    The status of the service. The valid values are ``ACTIVE`` , ``DRAINING`` , or ``INACTIVE`` .

    

    

  desiredCount -> (integer)

    

    The desired number of instantiations of the task definition to keep running on the service. This value is specified when the service is created with  create-service , and it can be modified with  update-service .

    

    

  runningCount -> (integer)

    

    The number of tasks in the cluster that are in the ``RUNNING`` state.

    

    

  pendingCount -> (integer)

    

    The number of tasks in the cluster that are in the ``PENDING`` state.

    

    

  taskDefinition -> (string)

    

    The task definition to use for tasks in the service. This value is specified when the service is created with  create-service , and it can be modified with  update-service .

    

    

  deploymentConfiguration -> (structure)

    

    Optional deployment parameters that control how many tasks run during the deployment and the ordering of stopping and starting tasks.

    

    maximumPercent -> (integer)

      

      The upper limit (as a percentage of the service's ``desiredCount`` ) of the number of running tasks that can be running in a service during a deployment. The maximum number of tasks during a deployment is the ``desiredCount`` multiplied by the ``maximumPercent`` /100, rounded down to the nearest integer value.

      

      

    minimumHealthyPercent -> (integer)

      

      The lower limit (as a percentage of the service's ``desiredCount`` ) of the number of running tasks that must remain running and healthy in a service during a deployment. The minimum healthy tasks during a deployment is the ``desiredCount`` multiplied by the ``minimumHealthyPercent`` /100, rounded up to the nearest integer value.

      

      

    

  deployments -> (list)

    

    The current state of deployments for the service.

    

    (structure)

      

      The details of an Amazon ECS service deployment.

      

      id -> (string)

        

        The ID of the deployment.

        

        

      status -> (string)

        

        The status of the deployment. Valid values are ``PRIMARY`` (for the most recent deployment), ``ACTIVE`` (for previous deployments that still have tasks running, but are being replaced with the ``PRIMARY`` deployment), and ``INACTIVE`` (for deployments that have been completely replaced).

        

        

      taskDefinition -> (string)

        

        The most recent task definition that was specified for the service to use.

        

        

      desiredCount -> (integer)

        

        The most recent desired count of tasks that was specified for the service to deploy or maintain.

        

        

      pendingCount -> (integer)

        

        The number of tasks in the deployment that are in the ``PENDING`` status.

        

        

      runningCount -> (integer)

        

        The number of tasks in the deployment that are in the ``RUNNING`` status.

        

        

      createdAt -> (timestamp)

        

        The Unix time in seconds and milliseconds when the service was created.

        

        

      updatedAt -> (timestamp)

        

        The Unix time in seconds and milliseconds when the service was last updated.

        

        

      

    

  roleArn -> (string)

    

    The Amazon Resource Name (ARN) of the IAM role associated with the service that allows the Amazon ECS container agent to register container instances with a load balancer. 

    

    

  events -> (list)

    

    The event stream for your service. A maximum of 100 of the latest events are displayed.

    

    (structure)

      

      Details on an event associated with a service.

      

      id -> (string)

        

        The ID string of the event.

        

        

      createdAt -> (timestamp)

        

        The Unix time in seconds and milliseconds when the event was triggered.

        

        

      message -> (string)

        

        The event message.

        

        

      

    

  

