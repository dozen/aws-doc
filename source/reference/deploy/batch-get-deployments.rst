[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy batch-get-deployments:


*********************
batch-get-deployments
*********************



===========
Description
===========



Gets information about one or more deployments.



========
Synopsis
========

::

    batch-get-deployments
  [--deployment-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--deployment-ids`` (list)


  A list of deployment IDs, with multiple deployment IDs separated by spaces.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

      

      

    revision -> (structure)

      

      Information about the location of application artifacts that are stored and the service to retrieve them from.

      

      revisionType -> (string)

        

        The application revision's type:

         

         
        * S3: An application revision stored in Amazon S3.
         
        * GitHub: An application revision stored in GitHub.
         

        

        

      s3Location -> (structure)

        

        Information about the location of application artifacts that are stored in Amazon S3.

        

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

        

        Information about the location of application artifacts that are stored in GitHub.

        

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

        

        The error code:

         

         
        * APPLICATION_MISSING: The application was missing. Note that this error code will most likely be raised if the application is deleted after the deployment is created but before it starts.
         
        * DEPLOYMENT_GROUP_MISSING: The deployment group was missing. Note that this error code will most likely be raised if the deployment group is deleted after the deployment is created but before it starts.
         
        * HEALTH_CONSTRAINTS: The deployment failed on too many instances to be able to successfully deploy within the specified instance health constraints.
         
        * HEALTH_CONSTRAINTS_INVALID: The revision can never successfully deploy within the instance health constraints as specified.
         
        * IAM_ROLE_MISSING: The service role cannot be accessed.
         
        * IAM_ROLE_PERMISSIONS: The service role does not have the correct permissions.
         
        * INTERNAL_ERROR: There was an internal error.
         
        * NO_EC2_SUBSCRIPTION: The calling account is not subscribed to the Amazon EC2 service.
         
        * NO_INSTANCES: No instances were specified, or no instances can be found.
         
        * OVER_MAX_INSTANCES: The maximum number of instances was exceeded.
         
        * THROTTLED: The operation was throttled because the calling account exceeded the throttling limits of one or more AWS services.
         
        * TIMEOUT: The deployment has timed out.
         
        * REVISION_MISSING: The revision ID was missing. Note that this error code will most likely be raised if the revision is deleted after the deployment is created but before it starts.
         

        

        

      message -> (string)

        

        An accompanying error message.

        

        

      

    createTime -> (timestamp)

      

      A timestamp indicating when the deployment was created.

      

      

    startTime -> (timestamp)

      

      A timestamp indicating when the deployment began deploying to the deployment group.

       

      Note that in some cases, the reported value of the start time may be later than the complete time. This is due to differences in the clock settings of various back-end servers that participate in the overall deployment process.

      

      

    completeTime -> (timestamp)

      

      A timestamp indicating when the deployment was completed.

      

      

    deploymentOverview -> (structure)

      

      A summary of the deployment status of the instances in the deployment.

      

      Pending -> (long)

        

        The number of instances that are pending in the deployment.

        

        

      InProgress -> (long)

        

        The number of instances that are in progress in the deployment.

        

        

      Succeeded -> (long)

        

        The number of instances that have succeeded in the deployment.

        

        

      Failed -> (long)

        

        The number of instances that have failed in the deployment.

        

        

      Skipped -> (long)

        

        The number of instances that have been skipped in the deployment.

        

        

      

    description -> (string)

      

      A comment about the deployment.

      

      

    creator -> (string)

      

      How the deployment was created:

       

       
      * user: A user created the deployment.
       
      * autoscaling: Auto Scaling created the deployment.
       

      

      

    ignoreApplicationStopFailures -> (boolean)

      

      If true, then if the deployment causes the ApplicationStop deployment lifecycle event to fail to a specific instance, the deployment will not be considered to have failed to that instance at that point and will continue on to the BeforeInstall deployment lifecycle event.

       

      If false or not specified, then if the deployment causes the ApplicationStop deployment lifecycle event to fail to a specific instance, the deployment will stop to that instance, and the deployment to that instance will be considered to have failed.

      

      

    

  

