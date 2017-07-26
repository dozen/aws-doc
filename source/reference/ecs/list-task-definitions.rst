[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs list-task-definitions:


*********************
list-task-definitions
*********************



===========
Description
===========



Returns a list of task definitions that are registered to your account. You can filter the results by family name with the ``familyPrefix`` parameter or by status with the ``status`` parameter.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecs-2014-11-13/ListTaskDefinitions>`_


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
  [--generate-cli-skeleton <value>]




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

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  

