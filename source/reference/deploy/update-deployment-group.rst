[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy update-deployment-group:


***********************
update-deployment-group
***********************



===========
Description
===========



Changes information about a deployment group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/UpdateDeploymentGroup>`_


========
Synopsis
========

::

    update-deployment-group
  --application-name <value>
  --current-deployment-group-name <value>
  [--new-deployment-group-name <value>]
  [--deployment-config-name <value>]
  [--on-premises-instance-tag-filters <value>]
  [--auto-scaling-groups <value>]
  [--service-role-arn <value>]
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


  The application name corresponding to the deployment group to update.

  

``--current-deployment-group-name`` (string)


  The current name of the deployment group.

  

``--new-deployment-group-name`` (string)


  The new name of the deployment group, if you want to change it.

  

``--deployment-config-name`` (string)


  The replacement deployment configuration name to use, if you want to change it.

  

``--on-premises-instance-tag-filters`` (list)


  The replacement set of on-premises instance tags on which to filter, if you want to change them. To keep the existing tags, enter their names. To remove tags, do not enter any tag names.

  



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


  The replacement list of Auto Scaling groups to be included in the deployment group, if you want to change them. To keep the Auto Scaling groups, enter their names. To remove Auto Scaling groups, do not enter any Auto Scaling group names.

  



Syntax::

  "string" "string" ...



``--service-role-arn`` (string)


  A replacement ARN for the service role, if you want to change it.

  

``--trigger-configurations`` (list)


  Information about triggers to change when the deployment group is updated. For examples, see `Modify Triggers in an AWS CodeDeploy Deployment Group <http://docs.aws.amazon.com/codedeploy/latest/userguide/how-to-notify-edit.html>`_ in the AWS CodeDeploy User Guide.

  



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


  Information to add or change about Amazon CloudWatch alarms when the deployment group is updated.

  



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


  Information for an automatic rollback configuration that is added or changed when a deployment group is updated.

  



Shorthand Syntax::

    enabled=boolean,events=string,string




JSON Syntax::

  {
    "enabled": true|false,
    "events": ["DEPLOYMENT_FAILURE"|"DEPLOYMENT_STOP_ON_ALARM"|"DEPLOYMENT_STOP_ON_REQUEST", ...]
  }



``--deployment-style`` (structure)


  Information about the type of deployment, either in-place or blue/green, you want to run and whether to route deployment traffic behind a load balancer.

  



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


  The replacement set of Amazon EC2 tags on which to filter, if you want to change them. To keep the existing tags, enter their names. To remove tags, do not enter any tag names.

  



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

**To change information about a deployment group**

This example changes the settings of a deployment group that is associated with the specified application.

Command::

  aws deploy update-deployment-group --application-name WordPress_App --auto-scaling-groups My_CodeDeployDemo_ASG --current-deployment-group-name WordPress_DG --deployment-config-name CodeDeployDefault.AllAtOnce --ec2-tag-filters Key=Name,Type=KEY_AND_VALUE,Value=My_CodeDeployDemo --new-deployment-group-name My_WordPress_DepGroup --service-role-arn arn:aws:iam::80398EXAMPLE:role/CodeDeployDemo-2

Output::

  None.

======
Output
======

hooksNotCleanedUp -> (list)

  

  If the output contains no data, and the corresponding deployment group contained at least one Auto Scaling group, AWS CodeDeploy successfully removed all corresponding Auto Scaling lifecycle event hooks from the AWS account. If the output contains data, AWS CodeDeploy could not remove some Auto Scaling lifecycle event hooks from the AWS account.

  

  (structure)

    

    Information about an Auto Scaling group.

    

    name -> (string)

      

      The Auto Scaling group name.

      

      

    hook -> (string)

      

      An Auto Scaling lifecycle event hook name.

      

      

    

  

