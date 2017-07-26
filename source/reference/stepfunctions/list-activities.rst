[ :ref:`aws <cli:aws>` . :ref:`stepfunctions <cli:aws stepfunctions>` ]

.. _cli:aws stepfunctions list-activities:


***************
list-activities
***************



===========
Description
===========



Lists the existing activities. The results may be split into multiple pages. To retrieve subsequent pages, make the call again using the ``nextToken`` returned by the previous call.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/states-2016-11-23/ListActivities>`_


``list-activities`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``activities``


========
Synopsis
========

::

    list-activities
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

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



======
Output
======

activities -> (list)

  

  The list of activities.

  

  (structure)

    

    activityArn -> (string)

      

      The Amazon Resource Name (ARN) that identifies the activity.

      

      

    name -> (string)

      

      The name of the activity.

      

      

    creationDate -> (timestamp)

      

      The date the activity was created.

      

      

    

  

nextToken -> (string)

  

  If a ``nextToken`` is returned, there are more results available. To retrieve the next page of results, make the call again using the returned token in ``nextToken`` . Keep all other arguments unchanged.

   

  The configured ``maxResults`` determines how many results can be returned in a single call.

  

  

