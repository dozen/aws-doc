[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs describe-clusters:


*****************
describe-clusters
*****************



===========
Description
===========



Describes one or more of your clusters.



========
Synopsis
========

::

    describe-clusters
  [--clusters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--clusters`` (list)


  A space-separated list of cluster names or full cluster Amazon Resource Name (ARN) entries. If you do not specify a cluster, the default cluster is assumed.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe a cluster**

This example command provides a description of the specified cluster in your default region.

Command::

  aws ecs describe-clusters --cluster default

Output::

	{
	    "clusters": [
	        {
	            "status": "ACTIVE",
	            "clusterName": "default",
	            "registeredContainerInstancesCount": 0,
	            "pendingTasksCount": 0,
	            "runningTasksCount": 0,
	            "activeServicesCount": 1,
	            "clusterArn": "arn:aws:ecs:us-west-2:<aws_Account_id>:cluster/default"
	        }
	    ],
	    "failures": []
	}


======
Output
======

clusters -> (list)

  

  The list of clusters.

  

  (structure)

    

    A regional grouping of one or more container instances on which you can run task requests. Each account receives a default cluster the first time you use the Amazon ECS service, but you may also create other clusters. Clusters may contain more than one instance type simultaneously.

    

    clusterArn -> (string)

      

      The Amazon Resource Name (ARN) that identifies the cluster. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the cluster, the AWS account ID of the cluster owner, the ``cluster`` namespace, and then the cluster name. For example, arn:aws:ecs:*region* :*012345678910* :cluster/*test* .

      

      

    clusterName -> (string)

      

      A user-generated string that you use to identify your cluster.

      

      

    status -> (string)

      

      The status of the cluster. The valid values are ``ACTIVE`` or ``INACTIVE`` . ``ACTIVE`` indicates that you can register container instances with the cluster and the associated instances can accept tasks.

      

      

    registeredContainerInstancesCount -> (integer)

      

      The number of container instances registered into the cluster.

      

      

    runningTasksCount -> (integer)

      

      The number of tasks in the cluster that are in the ``RUNNING`` state.

      

      

    pendingTasksCount -> (integer)

      

      The number of tasks in the cluster that are in the ``PENDING`` state.

      

      

    activeServicesCount -> (integer)

      

      The number of services that are running on the cluster in an ``ACTIVE`` state. You can view these services with  list-services .

      

      

    

  

failures -> (list)

  

  Any failures associated with the call.

  

  (structure)

    

    A failed resource.

    

    arn -> (string)

      

      The Amazon Resource Name (ARN) of the failed resource.

      

      

    reason -> (string)

      

      The reason for the failure.

      

      

    

  

