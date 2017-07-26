[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline get-pipeline-state:


******************
get-pipeline-state
******************



===========
Description
===========



Returns information about the state of a pipeline, including the stages, actions, and details about the last run of the pipeline.



========
Synopsis
========

::

    get-pipeline-state
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the pipeline about which you want to get information.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get information about the state of a pipeline**

This example returns the most recent state of a pipeline named MyFirstPipeline. 

Command::

  aws codepipeline get-pipeline-state --name MyFirstPipeline


Output::

  {
   "created": 1446137312.204,
   "pipelineName": "MyFirstPipeline",
   "pipelineVersion": 1,
   "stageStates": [
    {
      "actionStates": [
        {
          "actionName": "Source",
          "entityUrl": "https://console.aws.amazon.com/s3/home?#",
          "latestExecution": {
            "lastStatusChange": 1446137358.328,
            "status": "Succeeded"
          }
        }
      ],
      "stageName": "Source"
    },
    {
      "actionStates": [
        {
          "actionName": "CodePipelineDemoFleet",
          "entityUrl": "https://console.aws.amazon.com/codedeploy/home?#/applications/CodePipelineDemoApplication/deployment-groups/CodePipelineDemoFleet",
          "latestExecution": {
            "externalExecutionId": "d-EXAMPLE",
            "externalExecutionUrl": "https://console.aws.amazon.com/codedeploy/home?#/deployments/d-EXAMPLE",
            "lastStatusChange": 1446137493.131,
            "status": "Succeeded",
            "summary": "Deployment Succeeded"
          }
        }
      ],
      "inboundTransitionState": {
        "enabled": true
      },
      "stageName": "Beta"
    }
   ],
   "updated": 1446137312.204
  }

 

======
Output
======

pipelineName -> (string)

  

  The name of the pipeline for which you want to get the state.

  

  

pipelineVersion -> (integer)

  

  The version number of the pipeline.

   

  .. note::

    A newly-created pipeline is always assigned a version number of ``1`` .

  

  

stageStates -> (list)

  

  A list of the pipeline stage output information, including stage name, state, most recent run details, whether the stage is disabled, and other data. 

  

  (structure)

    

    Represents information about the state of the stage.

    

    stageName -> (string)

      

      The name of the stage.

      

      

    inboundTransitionState -> (structure)

      

      The state of the inbound transition, which is either enabled or disabled.

      

      enabled -> (boolean)

        

        Whether the transition between stages is enabled (true) or disabled (false).

        

        

      lastChangedBy -> (string)

        

        The ID of the user who last changed the transition state.

        

        

      lastChangedAt -> (timestamp)

        

        The timestamp when the transition state was last changed.

        

        

      disabledReason -> (string)

        

        The user-specified reason why the transition between two stages of a pipeline was disabled.

        

        

      

    actionStates -> (list)

      

      The state of the stage.

      

      (structure)

        

        Represents information about the state of an action.

        

        actionName -> (string)

          

          The name of the action.

          

          

        currentRevision -> (structure)

          

          Represents information about the version (or revision) of an action.

          

          revisionId -> (string)

            

            The system-generated unique ID that identifies the revision number of the action.

            

            

          revisionChangeId -> (string)

            

            The unique identifier of the change that set the state to this revision, for example a deployment ID or timestamp.

            

            

          created -> (timestamp)

            

            The date and time when the most recent version of the action was created, in timestamp format.

            

            

          

        latestExecution -> (structure)

          

          Represents information about how an action runs.

          

          status -> (string)

            

            The status of the action, or for a completed action, the last status of the action.

            

            

          summary -> (string)

            

            A summary of the run of the action.

            

            

          lastStatusChange -> (timestamp)

            

            The last status change of the action.

            

            

          externalExecutionId -> (string)

            

            The external ID of the run of the action.

            

            

          externalExecutionUrl -> (string)

            

            The URL of a resource external to AWS that will be used when running the action, for example an external repository URL.

            

            

          percentComplete -> (integer)

            

            A percentage of completeness of the action as it runs.

            

            

          errorDetails -> (structure)

            

            The details of an error returned by a URL external to AWS.

            

            code -> (string)

              

              The system ID or error number code of the error.

              

              

            message -> (string)

              

              The text of the error message.

              

              

            

          

        entityUrl -> (string)

          

          A URL link for more information about the state of the action, such as a deployment group details page.

          

          

        revisionUrl -> (string)

          

          A URL link for more information about the revision, such as a commit details page.

          

          

        

      

    

  

created -> (timestamp)

  

  The date and time the pipeline was created, in timestamp format.

  

  

updated -> (timestamp)

  

  The date and time the pipeline was last updated, in timestamp format.

  

  

