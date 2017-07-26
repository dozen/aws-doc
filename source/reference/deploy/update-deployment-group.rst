[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy update-deployment-group:


***********************
update-deployment-group
***********************



===========
Description
===========



Changes information about an existing deployment group.



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
  [--ec2-tag-filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The application name corresponding to the deployment group to update.

  

``--current-deployment-group-name`` (string)


  The current name of the existing deployment group.

  

``--new-deployment-group-name`` (string)


  The new name of the deployment group, if you want to change it.

  

``--deployment-config-name`` (string)


  The replacement deployment configuration name to use, if you want to change it.

  

``--on-premises-instance-tag-filters`` (list)


  The replacement set of on-premises instance tags for filter on, if you want to change them. To keep the existing tags, enter their names. To remove tags, do not enter any tag names.

  



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


  The replacement list of Auto Scaling groups to be included in the deployment group, if you want to change them. To keep the existing Auto Scaling groups, enter their names. To remove Auto Scaling groups, do not enter any Auto Scaling group names.

  



Syntax::

  "string" "string" ...



``--service-role-arn`` (string)


  A replacement service role's ARN, if you want to change it.

  

``--trigger-configurations`` (list)


  Information about triggers to change when the deployment group is updated.

  



Shorthand Syntax::

    triggerName=string,triggerTargetArn=string,triggerEvents=string,string ...




JSON Syntax::

  [
    {
      "triggerName": "string",
      "triggerTargetArn": "string",
      "triggerEvents": ["DeploymentStart"|"DeploymentSuccess"|"DeploymentFailure"|"DeploymentStop"|"InstanceStart"|"InstanceSuccess"|"InstanceFailure", ...]
    }
    ...
  ]



``--ec2-tag-filters`` (list)


  The replacement set of Amazon EC2 tags to filter on, if you want to change them. To keep the existing tags, enter their names. To remove tags, do not enter any tag names.

  



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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  If the output contains no data, and the corresponding deployment group contained at least one Auto Scaling group, AWS CodeDeploy successfully removed all corresponding Auto Scaling lifecycle event hooks from the AWS account. If the output does contain data, AWS CodeDeploy could not remove some Auto Scaling lifecycle event hooks from the AWS account.

  

  (structure)

    

    Information about an Auto Scaling group.

    

    name -> (string)

      

      The Auto Scaling group name.

      

      

    hook -> (string)

      

      An Auto Scaling lifecycle event hook name.

      

      

    

  

