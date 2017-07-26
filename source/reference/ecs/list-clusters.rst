[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs list-clusters:


*************
list-clusters
*************



===========
Description
===========



Returns a list of existing clusters.



``list-clusters`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``clusterArns``


========
Synopsis
========

::

    list-clusters
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

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

**To list your available clusters**

This example command lists all of your available clusters in your default region.

Command::

  aws ecs list-clusters

Output::

	{
	    "clusterArns": [
	        "arn:aws:ecs:us-east-1:<aws_account_id>:cluster/test",
	        "arn:aws:ecs:us-east-1:<aws_account_id>:cluster/default"
	    ]
	}


======
Output
======

clusterArns -> (list)

  

  The list of full Amazon Resource Name (ARN) entries for each cluster associated with your account.

  

  (string)

    

    

  

nextToken -> (string)

  

  The ``nextToken`` value to include in a future ``list-clusters`` request. When the results of a ``list-clusters`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

