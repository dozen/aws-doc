[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs create-cluster:


**************
create-cluster
**************



===========
Description
===========



Creates a new Amazon ECS cluster. By default, your account receives a ``default`` cluster when you launch your first container instance. However, you can create your own cluster with a unique name with the ``create-cluster`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecs-2014-11-13/CreateCluster>`_


========
Synopsis
========

::

    create-cluster
  [--cluster-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-name`` (string)


  The name of your cluster. If you do not specify a name for your cluster, you create a cluster named ``default`` . Up to 255 letters (uppercase and lowercase), numbers, hyphens, and underscores are allowed.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a new cluster**

This example command creates a cluster in your default region.

Command::

  aws ecs create-cluster --cluster-name "my_cluster"

Output::

	{
	    "cluster": {
	        "status": "ACTIVE",
	        "clusterName": "my_cluster",
	        "registeredContainerInstancesCount": 0,
	        "pendingTasksCount": 0,
	        "runningTasksCount": 0,
	        "activeServicesCount": 0,
	        "clusterArn": "arn:aws:ecs:<region>:<aws_account_id>:cluster/my_cluster"
	    }
	}


======
Output
======

cluster -> (structure)

  

  The full description of your new cluster.

  

  clusterArn -> (string)

    

    The Amazon Resource Name (ARN) that identifies the cluster. The ARN contains the ``arn:aws:ecs`` namespace, followed by the region of the cluster, the AWS account ID of the cluster owner, the ``cluster`` namespace, and then the cluster name. For example, ``arn:aws:ecs:*region* :*012345678910* :cluster/*test* `` ..

    

    

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

    

    

  

