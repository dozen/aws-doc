[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy create-deployment-group:


***********************
create-deployment-group
***********************



===========
Description
===========



Creates a deployment group to which application revisions will be deployed.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/CreateDeploymentGroup>`_


========
Synopsis
========

::

    create-deployment-group
  --application-name <value>
  --deployment-group-name <value>
  [--deployment-config-name <value>]
  [--on-premises-instance-tag-filters <value>]
  [--auto-scaling-groups <value>]
  --service-role-arn <value>
  [--trigger-configurations <value>]
  [--alarm-configuration <value>]
  [--auto-rollback-configuration <value>]
  [--deployment-style <value>]
  [--blue-green-deployment-configuration <value>]
  [--load-balancer-info <value>]
  [--ec2-tag-filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

  

``--deployment-group-name`` (string)


  The name of a new deployment group for the specified application.

  

``--deployment-config-name`` (string)


  If specified, the deployment configuration name can be either one of the predefined configurations provided with AWS CodeDeploy or a custom deployment configuration that you create by calling the create deployment configuration operation.

   

  CodeDeployDefault.OneAtATime is the default deployment configuration. It is used if a configuration isn't specified for the deployment or the deployment group.

   

  For more information about the predefined deployment configurations in AWS CodeDeploy, see `Working with Deployment Groups in AWS CodeDeploy <http://docs.aws.amazon.com/codedeploy/latest/userguide/deployment-configurations.html>`_ in the AWS CodeDeploy User Guide.

  

``--on-premises-instance-tag-filters`` (list)


  The on-premises instance tags on which to filter. The deployment group will include on-premises instances with any of the specified tags.

  



Shorthand Syntax::

    Key=string,Value=string,Type=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string",
      "Type": "KEY_ONLY"|"VALUE_ONLY"|"KEY_AND_VALUE"
    }
    ...
  ]



``--auto-scaling-groups`` (list)


  A list of associated Auto Scaling groups.

  



Syntax::

  "string" "string" ...



``--service-role-arn`` (string)


  A service role ARN that allows AWS CodeDeploy to act on the user's behalf when interacting with AWS services.

  

``--trigger-configurations`` (list)


  Information about triggers to create when the deployment group is created. For examples, see `Create a Trigger for an AWS CodeDeploy Event <http://docs.aws.amazon.com/codedeploy/latest/userguide/how-to-notify-sns.html>`_ in the AWS CodeDeploy User Guide.

  



Shorthand Syntax::

    triggerName=string,triggerTargetArn=string,triggerEvents=string,string ...




JSON Syntax::

  [
    {
      "triggerName": "string",
      "triggerTargetArn": "string",
      "triggerEvents": ["DeploymentStart"|"DeploymentSuccess"|"DeploymentFailure"|"DeploymentStop"|"DeploymentRollback"|"DeploymentReady"|"InstanceStart"|"InstanceSuccess"|"InstanceFailure"|"InstanceReady", ...]
    }
    ...
  ]



``--alarm-configuration`` (structure)


  Information to add about Amazon CloudWatch alarms when the deployment group is created.

  



Shorthand Syntax::

    enabled=boolean,ignorePollAlarmFailure=boolean,alarms=[{name=string},{name=string}]




JSON Syntax::

  {
    "enabled": true|false,
    "ignorePollAlarmFailure": true|false,
    "alarms": [
      {
        "name": "string"
      }
      ...
    ]
  }



``--auto-rollback-configuration`` (structure)


  Configuration information for an automatic rollback that is added when a deployment group is created.

  



Shorthand Syntax::

    enabled=boolean,events=string,string




JSON Syntax::

  {
    "enabled": true|false,
    "events": ["DEPLOYMENT_FAILURE"|"DEPLOYMENT_STOP_ON_ALARM"|"DEPLOYMENT_STOP_ON_REQUEST", ...]
  }



``--deployment-style`` (structure)


  Information about the type of deployment, in-place or blue/green, that you want to run and whether to route deployment traffic behind a load balancer.

  



Shorthand Syntax::

    deploymentType=string,deploymentOption=string




JSON Syntax::

  {
    "deploymentType": "IN_PLACE"|"BLUE_GREEN",
    "deploymentOption": "WITH_TRAFFIC_CONTROL"|"WITHOUT_TRAFFIC_CONTROL"
  }



``--blue-green-deployment-configuration`` (structure)


  Information about blue/green deployment options for a deployment group.

  



Shorthand Syntax::

    terminateBlueInstancesOnDeploymentSuccess={action=string,terminationWaitTimeInMinutes=integer},deploymentReadyOption={actionOnTimeout=string,waitTimeInMinutes=integer},greenFleetProvisioningOption={action=string}




JSON Syntax::

  {
    "terminateBlueInstancesOnDeploymentSuccess": {
      "action": "TERMINATE"|"KEEP_ALIVE",
      "terminationWaitTimeInMinutes": integer
    },
    "deploymentReadyOption": {
      "actionOnTimeout": "CONTINUE_DEPLOYMENT"|"STOP_DEPLOYMENT",
      "waitTimeInMinutes": integer
    },
    "greenFleetProvisioningOption": {
      "action": "DISCOVER_EXISTING"|"COPY_AUTO_SCALING_GROUP"
    }
  }



``--load-balancer-info`` (structure)


  Information about the load balancer used in a deployment.

  



Shorthand Syntax::

    elbInfoList=[{name=string},{name=string}]




JSON Syntax::

  {
    "elbInfoList": [
      {
        "name": "string"
      }
      ...
    ]
  }



``--ec2-tag-filters`` (list)


  The Amazon EC2 tags on which to filter. The deployment group will include EC2 instances with any of the specified tags.

  



Shorthand Syntax::

    Key=string,Value=string,Type=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string",
      "Type": "KEY_ONLY"|"VALUE_ONLY"|"KEY_AND_VALUE"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a deployment group**

This example creates a deployment group and associates it with the specified application and the user's AWS account.

Command::

  aws deploy create-deployment-group --application-name WordPress_App --auto-scaling-groups CodeDeployDemo-ASG --deployment-config-name CodeDeployDefault.OneAtATime --deployment-group-name WordPress_DG --ec2-tag-filters Key=Name,Value=CodeDeployDemo,Type=KEY_AND_VALUE --service-role-arn arn:aws:iam::80398EXAMPLE:role/CodeDeployDemoRole

Output::

  {
      "deploymentGroupId": "cdac3220-0e64-4d63-bb50-e68faEXAMPLE"
  }

======
Output
======

deploymentGroupId -> (string)

  

  A unique deployment group ID.

  

  

