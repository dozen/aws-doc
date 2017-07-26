[ :ref:`aws <cli:aws>` . :ref:`stepfunctions <cli:aws stepfunctions>` ]

.. _cli:aws stepfunctions get-execution-history:


*********************
get-execution-history
*********************



===========
Description
===========



Returns the history of the specified execution as a list of events. By default, the results are returned in ascending order of the ``timeStamp`` of the events. Use the ``reverseOrder`` parameter to get the latest events first. The results may be split into multiple pages. To retrieve subsequent pages, make the call again using the ``nextToken`` returned by the previous call.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/states-2016-11-23/GetExecutionHistory>`_


``get-execution-history`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``events``


========
Synopsis
========

::

    get-execution-history
  --execution-arn <value>
  [--reverse-order | --no-reverse-order]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--execution-arn`` (string)


  The Amazon Resource Name (ARN) of the execution.

  

``--reverse-order`` | ``--no-reverse-order`` (boolean)


  Lists events in descending order of their ``timeStamp`` .

  

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

events -> (list)

  

  The list of events that occurred in the execution.

  

  (structure)

    

    timestamp -> (timestamp)

      

      The date the event occured.

      

      

    type -> (string)

      

      The type of the event.

      

      

    id -> (long)

      

      The id of the event. Events are numbered sequentially, starting at one.

      

      

    previousEventId -> (long)

      

      The id of the previous event.

      

      

    activityFailedEventDetails -> (structure)

      

      error -> (string)

        

        The error code of the failure.

        

        

      cause -> (string)

        

        A more detailed explanation of the cause of the failure.

        

        

      

    activityScheduleFailedEventDetails -> (structure)

      

      error -> (string)

        

        The error code of the failure.

        

        

      cause -> (string)

        

        A more detailed explanation of the cause of the failure.

        

        

      

    activityScheduledEventDetails -> (structure)

      

      resource -> (string)

        

        The Amazon Resource Name (ARN) of the scheduled activity.

        

        

      input -> (string)

        

        The JSON data input to the activity task.

        

        

      timeoutInSeconds -> (long)

        

        The maximum allowed duration of the activity task.

        

        

      heartbeatInSeconds -> (long)

        

        The maximum allowed duration between two heartbeats for the activity task.

        

        

      

    activityStartedEventDetails -> (structure)

      

      workerName -> (string)

        

        The name of the worker that the task was assigned to. These names are provided by the workers when calling  get-activity-task .

        

        

      

    activitySucceededEventDetails -> (structure)

      

      output -> (string)

        

        The JSON data output by the activity task.

        

        

      

    activityTimedOutEventDetails -> (structure)

      

      error -> (string)

        

        The error code of the failure.

        

        

      cause -> (string)

        

        A more detailed explanation of the cause of the timeout.

        

        

      

    executionFailedEventDetails -> (structure)

      

      error -> (string)

        

        The error code of the failure.

        

        

      cause -> (string)

        

        A more detailed explanation of the cause of the failure.

        

        

      

    executionStartedEventDetails -> (structure)

      

      input -> (string)

        

        The JSON data input to the execution.

        

        

      roleArn -> (string)

        

        The Amazon Resource Name (ARN) of the IAM role used for executing AWS Lambda tasks.

        

        

      

    executionSucceededEventDetails -> (structure)

      

      output -> (string)

        

        The JSON data output by the execution.

        

        

      

    executionAbortedEventDetails -> (structure)

      

      error -> (string)

        

        The error code of the failure.

        

        

      cause -> (string)

        

        A more detailed explanation of the cause of the failure.

        

        

      

    executionTimedOutEventDetails -> (structure)

      

      error -> (string)

        

        The error code of the failure.

        

        

      cause -> (string)

        

        A more detailed explanation of the cause of the timeout.

        

        

      

    lambdaFunctionFailedEventDetails -> (structure)

      

      error -> (string)

        

        The error code of the failure.

        

        

      cause -> (string)

        

        A more detailed explanation of the cause of the failure.

        

        

      

    lambdaFunctionScheduleFailedEventDetails -> (structure)

      

      error -> (string)

        

        The error code of the failure.

        

        

      cause -> (string)

        

        A more detailed explanation of the cause of the failure.

        

        

      

    lambdaFunctionScheduledEventDetails -> (structure)

      

      resource -> (string)

        

        The Amazon Resource Name (ARN) of the scheduled lambda function.

        

        

      input -> (string)

        

        The JSON data input to the lambda function.

        

        

      timeoutInSeconds -> (long)

        

        The maximum allowed duration of the lambda function.

        

        

      

    lambdaFunctionStartFailedEventDetails -> (structure)

      

      error -> (string)

        

        The error code of the failure.

        

        

      cause -> (string)

        

        A more detailed explanation of the cause of the failure.

        

        

      

    lambdaFunctionSucceededEventDetails -> (structure)

      

      output -> (string)

        

        The JSON data output by the lambda function.

        

        

      

    lambdaFunctionTimedOutEventDetails -> (structure)

      

      error -> (string)

        

        The error code of the failure.

        

        

      cause -> (string)

        

        A more detailed explanation of the cause of the timeout.

        

        

      

    stateEnteredEventDetails -> (structure)

      

      name -> (string)

        

        The name of the state.

        

        

      input -> (string)

        

        The JSON input data to the state.

        

        

      

    stateExitedEventDetails -> (structure)

      

      name -> (string)

        

        The name of the state.

        

        

      output -> (string)

        

        The JSON output data of the state.

        

        

      

    

  

nextToken -> (string)

  

  If a ``nextToken`` is returned, there are more results available. To retrieve the next page of results, make the call again using the returned token in ``nextToken`` . Keep all other arguments unchanged.

   

  The configured ``maxResults`` determines how many results can be returned in a single call.

  

  

