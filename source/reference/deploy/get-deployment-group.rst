[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy get-deployment-group:


********************
get-deployment-group
********************



===========
Description
===========



Gets information about a deployment group.



========
Synopsis
========

::

    get-deployment-group
  --application-name <value>
  --deployment-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The name of an existing AWS CodeDeploy application associated with the applicable IAM user or AWS account.

  

``--deployment-group-name`` (string)


  The name of an existing deployment group for the specified application.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To view information about a deployment group**

This example displays information about a deployment group that is associated with the specified application.

Command::

  aws deploy get-deployment-group --application-name WordPress_App --deployment-group-name WordPress_DG

Output::

  {
      "deploymentGroupInfo": {
          "applicationName": "WordPress_App",
          "autoScalingGroups": [
		      "CodeDeployDemo-ASG"
	      ],
          "deploymentConfigName": "CodeDeployDefault.OneAtATime",
          "ec2TagFilters": [
              {
                  "Type": "KEY_AND_VALUE",
                  "Value": "CodeDeployDemo",
                  "Key": "Name"
              }
          ],
          "deploymentGroupId": "cdac3220-0e64-4d63-bb50-e68faEXAMPLE",
          "serviceRoleArn": "arn:aws:iam::80398EXAMPLE:role/CodeDeployDemoRole",
          "deploymentGroupName": "WordPress_DG"
      }
  }

======
Output
======

deploymentGroupInfo -> (structure)

  

  Information about the deployment group.

  

  applicationName -> (string)

    

    The application name.

    

    

  deploymentGroupId -> (string)

    

    The deployment group ID.

    

    

  deploymentGroupName -> (string)

    

    The deployment group name.

    

    

  deploymentConfigName -> (string)

    

    The deployment configuration name.

    

    

  ec2TagFilters -> (list)

    

    The Amazon EC2 tags to filter on.

    

    (structure)

      

      Information about a tag filter.

      

      Key -> (string)

        

        The tag filter key.

        

        

      Value -> (string)

        

        The tag filter value.

        

        

      Type -> (string)

        

        The tag filter type:

         

         
        * KEY_ONLY: Key only.
         
        * VALUE_ONLY: Value only.
         
        * KEY_AND_VALUE: Key and value.
         

        

        

      

    

  onPremisesInstanceTagFilters -> (list)

    

    The on-premises instance tags to filter on.

    

    (structure)

      

      Information about an on-premises instance tag filter.

      

      Key -> (string)

        

        The on-premises instance tag filter key.

        

        

      Value -> (string)

        

        The on-premises instance tag filter value.

        

        

      Type -> (string)

        

        The on-premises instance tag filter type:

         

         
        * KEY_ONLY: Key only.
         
        * VALUE_ONLY: Value only.
         
        * KEY_AND_VALUE: Key and value.
         

        

        

      

    

  autoScalingGroups -> (list)

    

    A list of associated Auto Scaling groups.

    

    (structure)

      

      Information about an Auto Scaling group.

      

      name -> (string)

        

        The Auto Scaling group name.

        

        

      hook -> (string)

        

        An Auto Scaling lifecycle event hook name.

        

        

      

    

  serviceRoleArn -> (string)

    

    A service role ARN.

    

    

  targetRevision -> (structure)

    

    Information about the deployment group's target revision, including the revision's type and its location.

    

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

        

        

      

    

  triggerConfigurations -> (list)

    

    A list of associated triggers. 

    

    (structure)

      

      Information about notification triggers for the deployment group.

      

      triggerName -> (string)

        The name of the notification trigger.

        

      triggerTargetArn -> (string)

        

        The arn of the Amazon Simple Notification Service topic through which notifications about deployment or instance events are sent.

        

        

      triggerEvents -> (list)

        

        The event type or types for which notifications are triggered.

         

        The following event type values are supported:

         

         
        * DEPLOYMENT_START
         
        * DEPLOYMENT_SUCCESS
         
        * DEPLOYMENT_FAILURE
         
        * DEPLOYMENT_STOP
         
        * INSTANCE_START
         
        * INSTANCE_SUCCESS
         
        * INSTANCE_FAILURE
         

        

        (string)

          

          

        

      

    

  

