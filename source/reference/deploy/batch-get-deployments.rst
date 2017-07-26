[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy batch-get-deployments:


*********************
batch-get-deployments
*********************



===========
Description
===========



Gets information about one or more deployments.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/BatchGetDeployments>`_


========
Synopsis
========

::

    batch-get-deployments
  [--deployment-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--deployment-ids`` (list)


  A list of deployment IDs, separated by spaces.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get information about multiple deployments**

This example displays information about multiple deployments that are associated with the user's AWS account.

Command::

  aws deploy batch-get-deployments --deployment-ids d-USUAELQEX d-QA4G4F9EX

Output::

  {
      "deploymentsInfo": [
          {
              "applicationName": "WordPress_App",
              "status": "Failed",
              "deploymentOverview": {
                  "Failed": 0,
                  "InProgress": 0,
                  "Skipped": 0,
                  "Succeeded": 1,
                  "Pending": 0
              },
              "deploymentConfigName": "CodeDeployDefault.OneAtATime",
              "creator": "user",
              "deploymentGroupName": "WordPress_DG",
			  "revision": {		  
                "revisionType": "S3",
                "s3Location": {
                  "bundleType": "zip",
                  "version": "uTecLusvCB_JqHFXtfUcyfV8bEXAMPLE",
                  "bucket": "CodeDeployDemoBucket",
                  "key": "WordPressApp.zip"
				}
              },
              "deploymentId": "d-QA4G4F9EX",
              "createTime": 1408480721.9,
              "completeTime": 1408480741.822
          },
          {
              "applicationName": "MyOther_App",
              "status": "Failed",
              "deploymentOverview": {
                  "Failed": 1,
                  "InProgress": 0,
                  "Skipped": 0,
                  "Succeeded": 0,
                  "Pending": 0
              },
              "deploymentConfigName": "CodeDeployDefault.OneAtATime",
              "creator": "user",
              "errorInformation": {
                  "message": "Deployment failed: Constraint default violated: No hosts succeeded.",
                  "code": "HEALTH_CONSTRAINTS"
              },
              "deploymentGroupName": "MyOther_DG",
			  "revision": {		  
                "revisionType": "S3",
                "s3Location": {
                  "bundleType": "zip",
                  "eTag": "\"dd56cfd59d434b8e768f9d77fEXAMPLE\"",
                  "bucket": "CodeDeployDemoBucket",
                  "key": "MyOtherApp.zip"
				}
              },
              "deploymentId": "d-USUAELQEX",
              "createTime": 1409764576.589,
              "completeTime": 1409764596.101
          }
      ]
  }


======
Output
======

deploymentsInfo -> (list)

  

  Information about the deployments.

  

  (structure)

    

    Information about a deployment.

    

    applicationName -> (string)

      

      The application name.

      

      

    deploymentGroupName -> (string)

      

      The deployment group name.

      

      

    deploymentConfigName -> (string)

      

      The deployment configuration name.

      

      

    deploymentId -> (string)

      

      The deployment ID.

      

      

    previousRevision -> (structure)

      

      Information about the application revision that was deployed to the deployment group before the most recent successful deployment.

      

      revisionType -> (string)

        

        The type of application revision:

         

         
        * S3: An application revision stored in Amazon S3. 
         
        * GitHub: An application revision stored in GitHub. 
         

        

        

      s3Location -> (structure)

        

        Information about the location of application artifacts stored in Amazon S3. 

        

        bucket -> (string)

          

          The name of the Amazon S3 bucket where the application revision is stored.

          

          

        key -> (string)

          

          The name of the Amazon S3 object that represents the bundled artifacts for the application revision.

          

          

        bundleType -> (string)

          

          The file type of the application revision. Must be one of the following:

           

           
          * tar: A tar archive file. 
           
          * tgz: A compressed tar archive file. 
           
          * zip: A zip archive file. 
           

          

          

        version -> (string)

          

          A specific version of the Amazon S3 object that represents the bundled artifacts for the application revision.

           

          If the version is not specified, the system will use the most recent version by default.

          

          

        eTag -> (string)

          

          The ETag of the Amazon S3 object that represents the bundled artifacts for the application revision.

           

          If the ETag is not specified as an input parameter, ETag validation of the object will be skipped.

          

          

        

      gitHubLocation -> (structure)

        

        Information about the location of application artifacts stored in GitHub.

        

        repository -> (string)

          

          The GitHub account and repository pair that stores a reference to the commit that represents the bundled artifacts for the application revision. 

           

          Specified as account/repository.

          

          

        commitId -> (string)

          

          The SHA1 commit ID of the GitHub commit that represents the bundled artifacts for the application revision.

          

          

        

      

    revision -> (structure)

      

      Information about the location of stored application artifacts and the service from which to retrieve them.

      

      revisionType -> (string)

        

        The type of application revision:

         

         
        * S3: An application revision stored in Amazon S3. 
         
        * GitHub: An application revision stored in GitHub. 
         

        

        

      s3Location -> (structure)

        

        Information about the location of application artifacts stored in Amazon S3. 

        

        bucket -> (string)

          

          The name of the Amazon S3 bucket where the application revision is stored.

          

          

        key -> (string)

          

          The name of the Amazon S3 object that represents the bundled artifacts for the application revision.

          

          

        bundleType -> (string)

          

          The file type of the application revision. Must be one of the following:

           

           
          * tar: A tar archive file. 
           
          * tgz: A compressed tar archive file. 
           
          * zip: A zip archive file. 
           

          

          

        version -> (string)

          

          A specific version of the Amazon S3 object that represents the bundled artifacts for the application revision.

           

          If the version is not specified, the system will use the most recent version by default.

          

          

        eTag -> (string)

          

          The ETag of the Amazon S3 object that represents the bundled artifacts for the application revision.

           

          If the ETag is not specified as an input parameter, ETag validation of the object will be skipped.

          

          

        

      gitHubLocation -> (structure)

        

        Information about the location of application artifacts stored in GitHub.

        

        repository -> (string)

          

          The GitHub account and repository pair that stores a reference to the commit that represents the bundled artifacts for the application revision. 

           

          Specified as account/repository.

          

          

        commitId -> (string)

          

          The SHA1 commit ID of the GitHub commit that represents the bundled artifacts for the application revision.

          

          

        

      

    status -> (string)

      

      The current state of the deployment as a whole.

      

      

    errorInformation -> (structure)

      

      Information about any error associated with this deployment.

      

      code -> (string)

        

        For information about additional error codes, see `Error Codes for AWS CodeDeploy <http://docs.aws.amazon.com/codedeploy/latest/userguide/error-codes.html>`_ in the `AWS CodeDeploy User Guide <http://docs.aws.amazon.com/codedeploy/latest/userguide>`_ .

         

        The error code:

         

         
        * APPLICATION_MISSING: The application was missing. This error code will most likely be raised if the application is deleted after the deployment is created but before it is started. 
         
        * DEPLOYMENT_GROUP_MISSING: The deployment group was missing. This error code will most likely be raised if the deployment group is deleted after the deployment is created but before it is started. 
         
        * HEALTH_CONSTRAINTS: The deployment failed on too many instances to be successfully deployed within the instance health constraints specified. 
         
        * HEALTH_CONSTRAINTS_INVALID: The revision cannot be successfully deployed within the instance health constraints specified. 
         
        * IAM_ROLE_MISSING: The service role cannot be accessed. 
         
        * IAM_ROLE_PERMISSIONS: The service role does not have the correct permissions. 
         
        * INTERNAL_ERROR: There was an internal error. 
         
        * NO_EC2_SUBSCRIPTION: The calling account is not subscribed to the Amazon EC2 service. 
         
        * NO_INSTANCES: No instance were specified, or no instance can be found. 
         
        * OVER_MAX_INSTANCES: The maximum number of instance was exceeded. 
         
        * THROTTLED: The operation was throttled because the calling account exceeded the throttling limits of one or more AWS services. 
         
        * TIMEOUT: The deployment has timed out. 
         
        * REVISION_MISSING: The revision ID was missing. This error code will most likely be raised if the revision is deleted after the deployment is created but before it is started. 
         

        

        

      message -> (string)

        

        An accompanying error message.

        

        

      

    createTime -> (timestamp)

      

      A timestamp indicating when the deployment was created.

      

      

    startTime -> (timestamp)

      

      A timestamp indicating when the deployment was deployed to the deployment group.

       

      In some cases, the reported value of the start time may be later than the complete time. This is due to differences in the clock settings of back-end servers that participate in the deployment process.

      

      

    completeTime -> (timestamp)

      

      A timestamp indicating when the deployment was complete.

      

      

    deploymentOverview -> (structure)

      

      A summary of the deployment status of the instances in the deployment.

      

      Pending -> (long)

        

        The number of instances in the deployment in a pending state.

        

        

      InProgress -> (long)

        

        The number of instances in which the deployment is in progress.

        

        

      Succeeded -> (long)

        

        The number of instances in the deployment to which revisions have been successfully deployed.

        

        

      Failed -> (long)

        

        The number of instances in the deployment in a failed state.

        

        

      Skipped -> (long)

        

        The number of instances in the deployment in a skipped state.

        

        

      Ready -> (long)

        

        The number of instances in a replacement environment ready to receive traffic in a blue/green deployment.

        

        

      

    description -> (string)

      

      A comment about the deployment.

      

      

    creator -> (string)

      

      The means by which the deployment was created:

       

       
      * user: A user created the deployment. 
       
      * autoscaling: Auto Scaling created the deployment. 
       
      * codeDeployRollback: A rollback process created the deployment. 
       

      

      

    ignoreApplicationStopFailures -> (boolean)

      

      If true, then if the deployment causes the ApplicationStop deployment lifecycle event to an instance to fail, the deployment to that instance will not be considered to have failed at that point and will continue on to the BeforeInstall deployment lifecycle event.

       

      If false or not specified, then if the deployment causes the ApplicationStop deployment lifecycle event to an instance to fail, the deployment to that instance will stop, and the deployment to that instance will be considered to have failed.

      

      

    autoRollbackConfiguration -> (structure)

      

      Information about the automatic rollback configuration associated with the deployment.

      

      enabled -> (boolean)

        

        Indicates whether a defined automatic rollback configuration is currently enabled.

        

        

      events -> (list)

        

        The event type or types that trigger a rollback.

        

        (string)

          

          

        

      

    updateOutdatedInstancesOnly -> (boolean)

      

      Indicates whether only instances that are not running the latest application revision are to be deployed to.

      

      

    rollbackInfo -> (structure)

      

      Information about a deployment rollback.

      

      rollbackDeploymentId -> (string)

        

        The ID of the deployment rollback.

        

        

      rollbackTriggeringDeploymentId -> (string)

        

        The deployment ID of the deployment that was underway and triggered a rollback deployment because it failed or was stopped.

        

        

      rollbackMessage -> (string)

        

        Information describing the status of a deployment rollback; for example, whether the deployment can't be rolled back, is in progress, failed, or succeeded. 

        

        

      

    deploymentStyle -> (structure)

      

      Information about the type of deployment, either in-place or blue/green, you want to run and whether to route deployment traffic behind a load balancer.

      

      deploymentType -> (string)

        

        Indicates whether to run an in-place deployment or a blue/green deployment.

        

        

      deploymentOption -> (string)

        

        Indicates whether to route deployment traffic behind a load balancer.

        

        

      

    targetInstances -> (structure)

      

      Information about the instances that belong to the replacement environment in a blue/green deployment.

      

      tagFilters -> (list)

        

        The tag filter key, type, and value used to identify Amazon EC2 instances in a replacement environment for a blue/green deployment.

        

        (structure)

          

          Information about an EC2 tag filter.

          

          Key -> (string)

            

            The tag filter key.

            

            

          Value -> (string)

            

            The tag filter value.

            

            

          Type -> (string)

            

            The tag filter type:

             

             
            * KEY_ONLY: Key only. 
             
            * VALUE_ONLY: Value only. 
             
            * KEY_AND_VALUE: Key and value. 
             

            

            

          

        

      autoScalingGroups -> (list)

        

        The names of one or more Auto Scaling groups to identify a replacement environment for a blue/green deployment.

        

        (string)

          

          

        

      

    instanceTerminationWaitTimeStarted -> (boolean)

      

      Indicates whether the wait period set for the termination of instances in the original environment has started. Status is 'false' if the KEEP_ALIVE option is specified; otherwise, 'true' as soon as the termination wait period starts.

      

      

    blueGreenDeploymentConfiguration -> (structure)

      

      Information about blue/green deployment options for this deployment.

      

      terminateBlueInstancesOnDeploymentSuccess -> (structure)

        

        Information about whether to terminate instances in the original fleet during a blue/green deployment.

        

        action -> (string)

          

          The action to take on instances in the original environment after a successful blue/green deployment.

           

           
          * TERMINATE: Instances are terminated after a specified wait time. 
           
          * KEEP_ALIVE: Instances are left running after they are deregistered from the load balancer and removed from the deployment group. 
           

          

          

        terminationWaitTimeInMinutes -> (integer)

          

          The number of minutes to wait after a successful blue/green deployment before terminating instances from the original environment.

          

          

        

      deploymentReadyOption -> (structure)

        

        Information about the action to take when newly provisioned instances are ready to receive traffic in a blue/green deployment.

        

        actionOnTimeout -> (string)

          

          Information about when to reroute traffic from an original environment to a replacement environment in a blue/green deployment.

           

           
          * CONTINUE_DEPLOYMENT: Register new instances with the load balancer immediately after the new application revision is installed on the instances in the replacement environment. 
           
          * STOP_DEPLOYMENT: Do not register new instances with load balancer unless traffic is rerouted manually. If traffic is not rerouted manually before the end of the specified wait period, the deployment status is changed to Stopped. 
           

          

          

        waitTimeInMinutes -> (integer)

          

          The number of minutes to wait before the status of a blue/green deployment changed to Stopped if rerouting is not started manually. Applies only to the STOP_DEPLOYMENT option for actionOnTimeout

          

          

        

      greenFleetProvisioningOption -> (structure)

        

        Information about how instances are provisioned for a replacement environment in a blue/green deployment.

        

        action -> (string)

          

          The method used to add instances to a replacement environment.

           

           
          * DISCOVER_EXISTING: Use instances that already exist or will be created manually. 
           
          * COPY_AUTO_SCALING_GROUP: Use settings from a specified Auto Scaling group to define and create instances in a new Auto Scaling group. 
           

          

          

        

      

    loadBalancerInfo -> (structure)

      

      Information about the load balancer used in the deployment.

      

      elbInfoList -> (list)

        

        An array containing information about the load balancer in Elastic Load Balancing to use in a deployment.

        

        (structure)

          

          Information about a load balancer in Elastic Load Balancing to use in a deployment.

          

          name -> (string)

            

            For blue/green deployments, the name of the load balancer that will be used to route traffic from original instances to replacement instances in a blue/green deployment. For in-place deployments, the name of the load balancer that instances are deregistered from so they are not serving traffic during a deployment, and then re-registered with after the deployment completes.

            

            

          

        

      

    additionalDeploymentStatusInfo -> (string)

      

      Provides information about the results of a deployment, such as whether instances in the original environment in a blue/green deployment were not terminated.

      

      

    fileExistsBehavior -> (string)

      

      Information about how AWS CodeDeploy handles files that already exist in a deployment target location but weren't part of the previous successful deployment.

       

       
      * DISALLOW: The deployment fails. This is also the default behavior if no option is specified. 
       
      * OVERWRITE: The version of the file from the application revision currently being deployed replaces the version already on the instance. 
       
      * RETAIN: The version of the file already on the instance is kept and used as part of the new deployment. 
       

      

      

    

  

