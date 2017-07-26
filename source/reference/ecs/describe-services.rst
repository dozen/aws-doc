[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs describe-services:


*****************
describe-services
*****************



===========
Description
===========



Describes the specified services running in your cluster.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecs-2014-11-13/DescribeServices>`_


========
Synopsis
========

::

    describe-services
  [--cluster <value>]
  --services <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN)the cluster that hosts the service to describe. If you do not specify a cluster, the default cluster is assumed.

  

``--services`` (list)


  A list of services to describe. You may specify up to 10 services to describe in a single operation.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a service**

This example command provides descriptive information about the ``my-http-service``.

Command::

  aws ecs describe-services --service my-http-service

Output::

  {
      "services": [
          {
              "status": "ACTIVE",
              "taskDefinition": "arn:aws:ecs:<region>:<aws_account_id>:task-definition/amazon-ecs-sample:1",
              "pendingCount": 0,
              "loadBalancers": [],
              "desiredCount": 10,
              "createdAt": 1466801808.595,
              "serviceName": "my-http-service",
              "clusterArn": "arn:aws:ecs:<region>:<aws_account_id>:cluster/default",
              "serviceArn": "arn:aws:ecs:<region>:<aws_account_id>:service/my-http-service",
              "deployments": [
                  {
                      "status": "PRIMARY",
                      "pendingCount": 0,
                      "createdAt": 1466801808.595,
                      "desiredCount": 10,
                      "taskDefinition": "arn:aws:ecs:<region>:<aws_account_id>:task-definition/amazon-ecs-sample:1",
                      "updatedAt": 1428326312.703,
                      "id": "ecs-svc/9223370608528463088",
                      "runningCount": 10
                  }
              ],
              "events": [
                  {
                      "message": "(service my-http-service) has reached a steady state.",
                      "id": "97c8a8e0-16a5-4d30-80bd-9e5413f8951b",
                      "createdAt": 1466801812.435
                  }
              ],
              "runningCount": 10
          }
      ],
      "failures": []
  }


======
Output
======

services -> (list)

  

  The list of services described.

  

  (structure)

    

    Details on a service within a cluster

    

    serviceArn -> (string)

      

      The Amazon Resource Name (ARN) that identifies the service. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the service, the AWS account ID of the service owner, the ``service`` namespace, and then the service name. For example, ``arn:aws:ecs:*region* :*012345678910* :service/*my-service* `` .

      

      

    serviceName -> (string)

      

      The name of your service. Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed. Service names must be unique within a cluster, but you can have similarly named services in multiple clusters within a region or across multiple regions.

      

      

    clusterArn -> (string)

      

      The Amazon Resource Name (ARN) of the cluster that hosts the service.

      

      

    loadBalancers -> (list)

      

      A list of Elastic Load Balancing load balancer objects, containing the load balancer name, the container name (as it appears in a container definition), and the container port to access from the load balancer.

      

      (structure)

        

        Details on a load balancer that is used with a service.

        

        targetGroupArn -> (string)

          

          The full Amazon Resource Name (ARN) of the Elastic Load Balancing target group associated with a service.

          

          

        loadBalancerName -> (string)

          

          The name of a Classic load balancer.

          

          

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

        

        The upper limit (as a percentage of the service's ``desiredCount`` ) of the number of tasks that are allowed in the ``RUNNING`` or ``PENDING`` state in a service during a deployment. The maximum number of tasks during a deployment is the ``desiredCount`` multiplied by ``maximumPercent`` /100, rounded down to the nearest integer value.

        

        

      minimumHealthyPercent -> (integer)

        

        The lower limit (as a percentage of the service's ``desiredCount`` ) of the number of running tasks that must remain in the ``RUNNING`` state in a service during a deployment. The minimum healthy tasks during a deployment is the ``desiredCount`` multiplied by ``minimumHealthyPercent`` /100, rounded up to the nearest integer value.

        

        

      

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

          

          The Unix timestamp for when the service was created.

          

          

        updatedAt -> (timestamp)

          

          The Unix timestamp for when the service was last updated.

          

          

        

      

    roleArn -> (string)

      

      The Amazon Resource Name (ARN) of the IAM role associated with the service that allows the Amazon ECS container agent to register container instances with an Elastic Load Balancing load balancer.

      

      

    events -> (list)

      

      The event stream for your service. A maximum of 100 of the latest events are displayed.

      

      (structure)

        

        Details on an event associated with a service.

        

        id -> (string)

          

          The ID string of the event.

          

          

        createdAt -> (timestamp)

          

          The Unix timestamp for when the event was triggered.

          

          

        message -> (string)

          

          The event message.

          

          

        

      

    createdAt -> (timestamp)

      

      The Unix timestamp for when the service was created.

      

      

    placementConstraints -> (list)

      

      The placement constraints for the tasks in the service.

      

      (structure)

        

        An object representing a constraint on task placement. For more information, see `Task Placement Constraints <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-placement-constraints.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

        

        type -> (string)

          

          The type of constraint. Use ``distinctInstance`` to ensure that each task in a particular group is running on a different container instance. Use ``memberOf`` to restrict selection to a group of valid candidates. Note that ``distinctInstance`` is not supported in task definitions.

          

          

        expression -> (string)

          

          A cluster query language expression to apply to the constraint. Note you cannot specify an expression if the constraint type is ``distinctInstance`` . For more information, see `Cluster Query Language <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/cluster-query-language.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

          

          

        

      

    placementStrategy -> (list)

      

      The placement strategy that determines how tasks for the service are placed.

      

      (structure)

        

        The task placement strategy for a task or service. For more information, see `Task Placement Strategies <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-placement-strategies.html>`_ in the *Amazon EC2 Container Service Developer Guide* .

        

        type -> (string)

          

          The type of placement strategy. The ``random`` placement strategy randomly places tasks on available candidates. The ``spread`` placement strategy spreads placement across available candidates evenly based on the ``field`` parameter. The ``binpack`` strategy places tasks on available candidates that have the least available amount of the resource that is specified with the ``field`` parameter. For example, if you binpack on memory, a task is placed on the instance with the least amount of remaining memory (but still enough to run the task).

          

          

        field -> (string)

          

          The field to apply the placement strategy against. For the ``spread`` placement strategy, valid values are ``instanceId`` (or ``host`` , which has the same effect), or any platform or custom attribute that is applied to a container instance, such as ``attribute:ecs.availability-zone`` . For the ``binpack`` placement strategy, valid values are ``cpu`` and ``memory`` . For the ``random`` placement strategy, this field is not used.

          

          

        

      

    

  

failures -> (list)

  

  Any failures associated with the call.

  

  (structure)

    

    A failed resource.

    

    arn -> (string)

      

      The Amazon Resource Name (ARN) of the failed resource.

      

      

    reason -> (string)

      

      The reason for the failure.

      

      

    

  

