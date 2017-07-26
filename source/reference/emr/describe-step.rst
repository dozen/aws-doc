[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr describe-step:


*************
describe-step
*************



===========
Description
===========



Provides more detail about the cluster step.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticmapreduce-2009-03-31/DescribeStep>`_


========
Synopsis
========

::

    describe-step
  --cluster-id <value>
  --step-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-id`` (string)


  The identifier of the cluster with steps to describe.

  

``--step-id`` (string)


  The identifier of the step to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command describes a step with the step ID ``s-3LZC0QUT43AM`` in a cluster with the cluster ID ``j-3SD91U2E1L2QX``::

  aws emr describe-step --cluster-id j-3SD91U2E1L2QX --step-id s-3LZC0QUT43AM

Output::

  {
      "Step": {
          "Status": {
              "Timeline": {
                  "EndDateTime": 1433200470.481,
                  "CreationDateTime": 1433199926.597,
                  "StartDateTime": 1433200404.959
              },
              "State": "COMPLETED",
              "StateChangeReason": {}
          },
          "Config": {
              "Args": [
                  "s3://us-west-2.elasticmapreduce/libs/hive/hive-script",
                  "--base-path",
                  "s3://us-west-2.elasticmapreduce/libs/hive/",
                  "--install-hive",
                  "--hive-versions",
                  "0.13.1"
              ],
              "Jar": "s3://us-west-2.elasticmapreduce/libs/script-runner/script-runner.jar",
              "Properties": {}
          },
          "Id": "s-3LZC0QUT43AM",
          "ActionOnFailure": "TERMINATE_CLUSTER",
          "Name": "Setup hive"
      }
  }


======
Output
======

Step -> (structure)

  

  The step details for the requested step identifier.

  

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

        

        

      

    

  

