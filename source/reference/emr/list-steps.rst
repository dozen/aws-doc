[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr list-steps:


**********
list-steps
**********



===========
Description
===========



Provides a list of steps for the cluster. 



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
  [--generate-cli-skeleton]




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

   

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  

