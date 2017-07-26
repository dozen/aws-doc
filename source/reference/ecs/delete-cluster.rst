[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs delete-cluster:


**************
delete-cluster
**************



===========
Description
===========



Deletes the specified cluster. You must deregister all container instances from this cluster before you may delete it. You can list the container instances in a cluster with  list-container-instances and deregister them with  deregister-container-instance .



========
Synopsis
========

::

    delete-cluster
  --cluster <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete an empty cluster**

This example command deletes an empty cluster in your default region.

Command::

  aws ecs delete-cluster --cluster my_cluster

Output::

	{
	    "cluster": {
	        "status": "INACTIVE",
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

  

  The full description of the deleted cluster.

  

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

    

    

  

