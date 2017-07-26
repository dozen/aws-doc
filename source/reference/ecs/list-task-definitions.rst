[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs list-task-definitions:


*********************
list-task-definitions
*********************



===========
Description
===========



Returns a list of task definitions that are registered to your account. You can filter the results by family name with the ``familyPrefix`` parameter or by status with the ``status`` parameter.



``list-task-definitions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``taskDefinitionArns``


========
Synopsis
========

::

    list-task-definitions
  [--family-prefix <value>]
  [--status <value>]
  [--sort <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--family-prefix`` (string)


  The full family name with which to filter the ``list-task-definitions`` results. Specifying a ``familyPrefix`` limits the listed task definitions to task definition revisions that belong to that family.

  

``--status`` (string)


  The task definition status with which to filter the ``list-task-definitions`` results. By default, only ``ACTIVE`` task definitions are listed. By setting this parameter to ``INACTIVE`` , you can view task definitions that are ``INACTIVE`` as long as an active task or service still references them. If you paginate the resulting output, be sure to keep the ``status`` value constant in each subsequent request.

  

  Possible values:

  
  *   ``ACTIVE``

  
  *   ``INACTIVE``

  

  

``--sort`` (string)


  The order in which to sort the results. Valid values are ``ASC`` and ``DESC`` . By default (``ASC`` ), task definitions are listed lexicographically by family name and in ascending numerical order by revision so that the newest task definitions in a family are listed last. Setting this parameter to ``DESC`` reverses the sort order on family name and revision so that the newest task definitions in a family are listed first.

  

  Possible values:

  
  *   ``ASC``

  
  *   ``DESC``

  

  

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

**To list your registered task definitions**

This example command lists all of your registered task definitions.

Command::

  aws ecs list-task-definitions

Output::

	{
	    "taskDefinitionArns": [
	        "arn:aws:ecs:us-east-1:<aws_account_id>:task-definition/sleep300:2",
	        "arn:aws:ecs:us-east-1:<aws_account_id>:task-definition/sleep360:1",
	        "arn:aws:ecs:us-east-1:<aws_account_id>:task-definition/wordpress:3",
	        "arn:aws:ecs:us-east-1:<aws_account_id>:task-definition/wordpress:4",
	        "arn:aws:ecs:us-east-1:<aws_account_id>:task-definition/wordpress:5",
	        "arn:aws:ecs:us-east-1:<aws_account_id>:task-definition/wordpress:6"
	    ]
	}

**To list the registered task definitions in a family**

This example command lists the task definition revisions of a specified family.

Command::

  aws ecs list-task-definitions --family-prefix wordpress

Output::

	{
	    "taskDefinitionArns": [
	        "arn:aws:ecs:us-east-1:<aws_account_id>:task-definition/wordpress:3",
	        "arn:aws:ecs:us-east-1:<aws_account_id>:task-definition/wordpress:4",
	        "arn:aws:ecs:us-east-1:<aws_account_id>:task-definition/wordpress:5",
	        "arn:aws:ecs:us-east-1:<aws_account_id>:task-definition/wordpress:6"
	    ]
	}

======
Output
======

taskDefinitionArns -> (list)

  

  The list of task definition Amazon Resource Name (ARN) entries for the ``list-task-definitions`` request.

  

  (string)

    

    

  

nextToken -> (string)

  

  The ``nextToken`` value to include in a future ``list-task-definitions`` request. When the results of a ``list-task-definitions`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

