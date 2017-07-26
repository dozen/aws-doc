[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy batch-get-deployment-instances:


******************************
batch-get-deployment-instances
******************************



===========
Description
===========



Gets information about one or more instance that are part of a deployment group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/BatchGetDeploymentInstances>`_


========
Synopsis
========

::

    batch-get-deployment-instances
  --deployment-id <value>
  --instance-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--deployment-id`` (string)


  The unique ID of a deployment.

  

``--instance-ids`` (list)


  The unique IDs of instances in the deployment group.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

instancesSummary -> (list)

  

  Information about the instance.

  

  (structure)

    

    Information about an instance in a deployment.

    

    deploymentId -> (string)

      

      The deployment ID.

      

      

    instanceId -> (string)

      

      The instance ID.

      

      

    status -> (string)

      

      The deployment status for this instance:

       

       
      * Pending: The deployment is pending for this instance. 
       
      * In Progress: The deployment is in progress for this instance. 
       
      * Succeeded: The deployment has succeeded for this instance. 
       
      * Failed: The deployment has failed for this instance. 
       
      * Skipped: The deployment has been skipped for this instance. 
       
      * Unknown: The deployment status is unknown for this instance. 
       

      

      

    lastUpdatedAt -> (timestamp)

      

      A timestamp indicating when the instance information was last updated.

      

      

    lifecycleEvents -> (list)

      

      A list of lifecycle events for this instance.

      

      (structure)

        

        Information about a deployment lifecycle event.

        

        lifecycleEventName -> (string)

          

          The deployment lifecycle event name, such as ApplicationStop, BeforeInstall, AfterInstall, ApplicationStart, or ValidateService.

          

          

        diagnostics -> (structure)

          

          Diagnostic information about the deployment lifecycle event.

          

          errorCode -> (string)

            

            The associated error code:

             

             
            * Success: The specified script ran. 
             
            * ScriptMissing: The specified script was not found in the specified location. 
             
            * ScriptNotExecutable: The specified script is not a recognized executable file type. 
             
            * ScriptTimedOut: The specified script did not finish running in the specified time period. 
             
            * ScriptFailed: The specified script failed to run as expected. 
             
            * UnknownError: The specified script did not run for an unknown reason. 
             

            

            

          scriptName -> (string)

            

            The name of the script.

            

            

          message -> (string)

            

            The message associated with the error.

            

            

          logTail -> (string)

            

            The last portion of the diagnostic log.

             

            If available, AWS CodeDeploy returns up to the last 4 KB of the diagnostic log.

            

            

          

        startTime -> (timestamp)

          

          A timestamp indicating when the deployment lifecycle event started.

          

          

        endTime -> (timestamp)

          

          A timestamp indicating when the deployment lifecycle event ended.

          

          

        status -> (string)

          

          The deployment lifecycle event status:

           

           
          * Pending: The deployment lifecycle event is pending. 
           
          * InProgress: The deployment lifecycle event is in progress. 
           
          * Succeeded: The deployment lifecycle event ran successfully. 
           
          * Failed: The deployment lifecycle event has failed. 
           
          * Skipped: The deployment lifecycle event has been skipped. 
           
          * Unknown: The deployment lifecycle event is unknown. 
           

          

          

        

      

    instanceType -> (string)

      

      Information about which environment an instance belongs to in a blue/green deployment.

       

       
      * BLUE: The instance is part of the original environment. 
       
      * GREEN: The instance is part of the replacement environment. 
       

      

      

    

  

errorMessage -> (string)

  

  Information about errors that may have occurred during the API call.

  

  

