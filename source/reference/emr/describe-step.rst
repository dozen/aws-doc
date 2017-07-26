[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr describe-step:


*************
describe-step
*************



===========
Description
===========



Provides more detail about the cluster step.



========
Synopsis
========

::

    describe-step
  --cluster-id <value>
  --step-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster-id`` (string)


  The identifier of the cluster with steps to describe.

  

``--step-id`` (string)


  The identifier of the step to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

        

        

      

    Timeline -> (structure)

      

      The timeline of the cluster step status over time. 

      

      CreationDateTime -> (timestamp)

        

        The date and time when the cluster step was created. 

        

        

      StartDateTime -> (timestamp)

        

        The date and time when the cluster step execution started. 

        

        

      EndDateTime -> (timestamp)

        

        The date and time when the cluster step execution completed or failed. 

        

        

      

    

  

