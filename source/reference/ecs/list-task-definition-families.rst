[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs list-task-definition-families:


*****************************
list-task-definition-families
*****************************



===========
Description
===========



Returns a list of task definition families that are registered to your account (which may include task definition families that no longer have any ``ACTIVE`` task definition revisions).

 

You can filter out task definition families that do not contain any ``ACTIVE`` task definition revisions by setting the ``status`` parameter to ``ACTIVE`` . You can also filter the results with the ``familyPrefix`` parameter.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecs-2014-11-13/ListTaskDefinitionFamilies>`_


``list-task-definition-families`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``families``


========
Synopsis
========

::

    list-task-definition-families
  [--family-prefix <value>]
  [--status <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--family-prefix`` (string)


  The ``familyPrefix`` is a string that is used to filter the results of ``list-task-definition-families`` . If you specify a ``familyPrefix`` , only task definition family names that begin with the ``familyPrefix`` string are returned.

  

``--status`` (string)


  The task definition family status with which to filter the ``list-task-definition-families`` results. By default, both ``ACTIVE`` and ``INACTIVE`` task definition families are listed. If this parameter is set to ``ACTIVE`` , only task definition families that have an ``ACTIVE`` task definition revision are returned. If this parameter is set to ``INACTIVE`` , only task definition families that do not have any ``ACTIVE`` task definition revisions are returned. If you paginate the resulting output, be sure to keep the ``status`` value constant in each subsequent request.

  

  Possible values:

  
  *   ``ACTIVE``

  
  *   ``INACTIVE``

  
  *   ``ALL``

  

  

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

  

  

