[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs list-task-definition-families:


*****************************
list-task-definition-families
*****************************



===========
Description
===========



Returns a list of task definition families that are registered to your account (which may include task definition families that no longer have any ``ACTIVE`` task definitions). You can filter the results with the ``familyPrefix`` parameter.



``list-task-definition-families`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``families``


========
Synopsis
========

::

    list-task-definition-families
  [--family-prefix <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--family-prefix`` (string)


  The ``familyPrefix`` is a string that is used to filter the results of ``list-task-definition-families`` . If you specify a ``familyPrefix`` , only task definition family names that begin with the ``familyPrefix`` string are returned.

  

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

**To list your registered task definition families**

This example command lists all of your registered task definition families.

Command::

  aws ecs list-task-definition-families

Output::

	{
	    "families": [
	        "node-js-app",
	        "web-timer",
	        "hpcc",
	        "hpcc-c4-8xlarge"
	    ]
	}

**To filter your registered task definition families**

This example command lists the task definition revisions that start with "hpcc".

Command::

  aws ecs list-task-definition-families --family-prefix hpcc

Output::

	{
	    "families": [
	        "hpcc",
	        "hpcc-c4-8xlarge"
	    ]
	}


======
Output
======

families -> (list)

  

  The list of task definition family names that match the ``list-task-definition-families`` request.

  

  (string)

    

    

  

nextToken -> (string)

  

  The ``nextToken`` value to include in a future ``list-task-definition-families`` request. When the results of a ``list-task-definition-families`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

