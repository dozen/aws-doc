[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr list-steps:


**********
list-steps
**********



===========
Description
===========



Provides a list of steps for the cluster in reverse order unless you specify stepIds with the request.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticmapreduce-2009-03-31/ListSteps>`_


``list-steps`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Steps``


========
Synopsis
========

::

    list-steps
  --cluster-id <value>
  [--step-states <value>]
  [--step-ids <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-id`` (string)


  The identifier of the cluster for which to list the steps.

  

``--step-states`` (list)


  The filter to limit the step list based on certain states.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    PENDING
    CANCEL_PENDING
    RUNNING
    COMPLETED
    CANCELLED
    FAILED
    INTERRUPTED





``--step-ids`` (list)


  The filter to limit the step list based on the identifier of the steps.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command lists all of the steps in a cluster with the cluster ID ``j-3SD91U2E1L2QX``::

  aws emr list-steps --cluster-id j-3SD91U2E1L2QX


======
Output
======

Steps -> (list)

  

  The filtered list of steps for the cluster.

  

  (structure)

    

    The summary of the cluster step.

    

    Id -> (string)

      

      The identifier of the cluster step.

      

      

    Name -> (string)

      

      The name of the cluster step.

      

      

    Config -> (structure)

      

      The Hadoop job configuration of the cluster step.

      

      Jar -> (string)

        

        The path to the JAR file that runs during the step.

        

        

      Properties -> (map)

        

        The list of Java properties that are set when the step runs. You can use these properties to pass key value pairs to your main function.

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      MainClass -> (string)

        

        The name of the main class in the specified Java file. If not specified, the JAR file should specify a main class in its manifest file.

        

        

      Args -> (list)

        

        The list of command line arguments to pass to the JAR file's main function for execution.

        

        (string)

          

          

        

      

    ActionOnFailure -> (string)

      

      This specifies what action to take when the cluster step fails. Possible values are TERMINATE_CLUSTER, CANCEL_AND_WAIT, and CONTINUE.

      

      

    Status -> (structure)

      

      The current execution status details of the cluster step.

      

      State -> (string)

        

        The execution state of the cluster step.

        

        

      StateChangeReason -> (structure)

        

        The reason for the step execution status change.

        

        Code -> (string)

          

          The programmable code for the state change reason. Note: Currently, the service provides no code for the state change.

          

          

        Message -> (string)

          

          The descriptive message for the state change reason.

          

          

        

      FailureDetails -> (structure)

        

        The details for the step failure including reason, message, and log file path where the root cause was identified.

        

        Reason -> (string)

          

          The reason for the step failure. In the case where the service cannot successfully determine the root cause of the failure, it returns "Unknown Error" as a reason.

          

          

        Message -> (string)

          

          The descriptive message including the error the EMR service has identified as the cause of step failure. This is text from an error log that describes the root cause of the failure.

          

          

        LogFile -> (string)

          

          The path to the log file where the step failure root cause was originally recorded.

          

          

        

      Timeline -> (structure)

        

        The timeline of the cluster step status over time.

        

        CreationDateTime -> (timestamp)

          

          The date and time when the cluster step was created.

          

          

        StartDateTime -> (timestamp)

          

          The date and time when the cluster step execution started.

          

          

        EndDateTime -> (timestamp)

          

          The date and time when the cluster step execution completed or failed.

          

          

        

      

    

  

Marker -> (string)

  

  The pagination token that indicates the next set of results to retrieve.

  

  

