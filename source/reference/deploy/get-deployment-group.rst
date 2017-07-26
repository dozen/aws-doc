[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy get-deployment-group:


********************
get-deployment-group
********************



===========
Description
===========



Gets information about a deployment group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/GetDeploymentGroup>`_


========
Synopsis
========

::

    get-deployment-group
  --application-name <value>
  --deployment-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

  

``--deployment-group-name`` (string)


  The name of an existing deployment group for the specified application.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    The Amazon EC2 tags on which to filter.

    

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
         

        

        

      

    

  onPremisesInstanceTagFilters -> (list)

    

    The on-premises instance tags on which to filter.

    

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

    

    Information about the deployment group's target revision, including type and location.

    

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

        

        

      

    

  triggerConfigurations -> (list)

    

    Information about triggers associated with the deployment group.

    

    (structure)

      

      Information about notification triggers for the deployment group.

      

      triggerName -> (string)

        

        The name of the notification trigger.

        

        

      triggerTargetArn -> (string)

        

        The ARN of the Amazon Simple Notification Service topic through which notifications about deployment or instance events are sent.

        

        

      triggerEvents -> (list)

        

        The event type or types for which notifications are triggered.

        

        (string)

          

          

        

      

    

  alarmConfiguration -> (structure)

    

    A list of alarms associated with the deployment group.

    

    enabled -> (boolean)

      

      Indicates whether the alarm configuration is enabled.

      

      

    ignorePollAlarmFailure -> (boolean)

      

      Indicates whether a deployment should continue if information about the current state of alarms cannot be retrieved from Amazon CloudWatch. The default value is false.

       

       
      * true: The deployment will proceed even if alarm status information can't be retrieved from Amazon CloudWatch. 
       
      * false: The deployment will stop if alarm status information can't be retrieved from Amazon CloudWatch. 
       

      

      

    alarms -> (list)

      

      A list of alarms configured for the deployment group. A maximum of 10 alarms can be added to a deployment group.

      

      (structure)

        

        Information about an alarm.

        

        name -> (string)

          

          The name of the alarm. Maximum length is 255 characters. Each alarm name can be used only once in a list of alarms.

          

          

        

      

    

  autoRollbackConfiguration -> (structure)

    

    Information about the automatic rollback configuration associated with the deployment group.

    

    enabled -> (boolean)

      

      Indicates whether a defined automatic rollback configuration is currently enabled.

      

      

    events -> (list)

      

      The event type or types that trigger a rollback.

      

      (string)

        

        

      

    

  deploymentStyle -> (structure)

    

    Information about the type of deployment, either in-place or blue/green, you want to run and whether to route deployment traffic behind a load balancer.

    

    deploymentType -> (string)

      

      Indicates whether to run an in-place deployment or a blue/green deployment.

      

      

    deploymentOption -> (string)

      

      Indicates whether to route deployment traffic behind a load balancer.

      

      

    

  blueGreenDeploymentConfiguration -> (structure)

    

    Information about blue/green deployment options for a deployment group.

    

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

    

    Information about the load balancer to use in a deployment.

    

    elbInfoList -> (list)

      

      An array containing information about the load balancer in Elastic Load Balancing to use in a deployment.

      

      (structure)

        

        Information about a load balancer in Elastic Load Balancing to use in a deployment.

        

        name -> (string)

          

          For blue/green deployments, the name of the load balancer that will be used to route traffic from original instances to replacement instances in a blue/green deployment. For in-place deployments, the name of the load balancer that instances are deregistered from so they are not serving traffic during a deployment, and then re-registered with after the deployment completes.

          

          

        

      

    

  lastSuccessfulDeployment -> (structure)

    

    Information about the most recent successful deployment to the deployment group.

    

    deploymentId -> (string)

      

      The deployment ID.

      

      

    status -> (string)

      

      The status of the most recent deployment.

      

      

    endTime -> (timestamp)

      

      A timestamp indicating when the most recent deployment to the deployment group completed.

      

      

    createTime -> (timestamp)

      

      A timestamp indicating when the most recent deployment to the deployment group started.

      

      

    

  lastAttemptedDeployment -> (structure)

    

    Information about the most recent attempted deployment to the deployment group.

    

    deploymentId -> (string)

      

      The deployment ID.

      

      

    status -> (string)

      

      The status of the most recent deployment.

      

      

    endTime -> (timestamp)

      

      A timestamp indicating when the most recent deployment to the deployment group completed.

      

      

    createTime -> (timestamp)

      

      A timestamp indicating when the most recent deployment to the deployment group started.

      

      

    

  

