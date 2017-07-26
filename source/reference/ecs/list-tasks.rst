[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs list-tasks:


**********
list-tasks
**********



===========
Description
===========



Returns a list of tasks for a specified cluster. You can filter the results by family name, by a particular container instance, or by the desired status of the task with the ``family`` , ``containerInstance`` , and ``desiredStatus`` parameters.



``list-tasks`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``taskArns``


========
Synopsis
========

::

    list-tasks
  [--cluster <value>]
  [--container-instance <value>]
  [--family <value>]
  [--started-by <value>]
  [--service-name <value>]
  [--desired-status <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster that hosts the tasks to list. If you do not specify a cluster, the default cluster is assumed..

  

``--container-instance`` (string)


  The container instance ID or full Amazon Resource Name (ARN) of the container instance with which to filter the ``list-tasks`` results. Specifying a ``containerInstance`` limits the results to tasks that belong to that container instance.

  

``--family`` (string)


  The name of the family with which to filter the ``list-tasks`` results. Specifying a ``family`` limits the results to tasks that belong to that family.

  

``--started-by`` (string)


  The ``startedBy`` value with which to filter the task results. Specifying a ``startedBy`` value limits the results to tasks that were started with that value.

  

``--service-name`` (string)


  The name of the service with which to filter the ``list-tasks`` results. Specifying a ``serviceName`` limits the results to tasks that belong to that service.

  

``--desired-status`` (string)


  The task status with which to filter the ``list-tasks`` results. Specifying a ``desiredStatus`` of ``STOPPED`` limits the results to tasks that are in the ``STOPPED`` status, which can be useful for debugging tasks that are not starting properly or have died or finished. The default status filter is ``RUNNING`` .

  

  Possible values:

  
  *   ``RUNNING``

  
  *   ``PENDING``

  
  *   ``STOPPED``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To list the tasks in a cluster**

This example command lists all of the tasks in a cluster.

Command::

  aws ecs list-tasks --cluster default

Output::

	{
	    "taskArns": [
	        "arn:aws:ecs:us-east-1:<aws_account_id>:task/0cc43cdb-3bee-4407-9c26-c0e6ea5bee84",
	        "arn:aws:ecs:us-east-1:<aws_account_id>:task/6b809ef6-c67e-4467-921f-ee261c15a0a1"
	    ]
	}

**To list the tasks on a particular container instance**

This example command lists the tasks of a specified container instance, using the container instance UUID as a filter.

Command::

  aws ecs list-tasks --cluster default --container-instance f6bbb147-5370-4ace-8c73-c7181ded911f

Output::

	{
	    "taskArns": [
	        "arn:aws:ecs:us-east-1:<aws_account_id>:task/0cc43cdb-3bee-4407-9c26-c0e6ea5bee84"
	    ]
	}

======
Output
======

taskArns -> (list)

  

  The list of task Amazon Resource Name (ARN) entries for the ``list-tasks`` request.

  

  (string)

    

    

  

nextToken -> (string)

  

  The ``nextToken`` value to include in a future ``list-tasks`` request. When the results of a ``list-tasks`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

