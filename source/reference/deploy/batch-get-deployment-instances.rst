[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy batch-get-deployment-instances:


******************************
batch-get-deployment-instances
******************************



===========
Description
===========



Gets information about one or more instances that are part of a deployment group.



========
Synopsis
========

::

    batch-get-deployment-instances
  --deployment-id <value>
  --instance-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--deployment-id`` (string)


  The unique ID of a deployment.

  

``--instance-ids`` (list)


  The unique IDs of instances in the deployment's deployment group.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

instancesSummary -> (list)

  

  Information about the instances.

  

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

            

            The last portion of the associated diagnostic log.

             

            If available, AWS CodeDeploy returns up to the last 4 KB of the associated diagnostic log.

            

            

          

        startTime -> (timestamp)

          

          A timestamp indicating when the deployment lifecycle event started.

          

          

        endTime -> (timestamp)

          

          A timestamp indicating when the deployment lifecycle event ended.

          

          

        status -> (string)

          

          The deployment lifecycle event status:

           

           
          * Pending: The deployment lifecycle event is pending.
           
          * InProgress: The deployment lifecycle event is in progress.
           
          * Succeeded: The deployment lifecycle event has succeeded.
           
          * Failed: The deployment lifecycle event has failed.
           
          * Skipped: The deployment lifecycle event has been skipped.
           
          * Unknown: The deployment lifecycle event is unknown.
           

          

          

        

      

    

  

errorMessage -> (string)

  

  Information about errors that may have occurred during the API call.

  

  

