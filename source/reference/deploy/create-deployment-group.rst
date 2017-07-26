[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy create-deployment-group:


***********************
create-deployment-group
***********************



===========
Description
===========



Creates a new deployment group for application revisions to be deployed to.



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
  [--ec2-tag-filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The name of an existing AWS CodeDeploy application associated with the applicable IAM user or AWS account.

  

``--deployment-group-name`` (string)


  The name of a new deployment group for the specified application.

  

``--deployment-config-name`` (string)


  If specified, the deployment configuration name can be either one of the predefined configurations provided with AWS CodeDeploy, or a custom deployment configuration that you created by calling the create deployment configuration operation.

   

  .. note::

     

    CodeDeployDefault.OneAtATime is the default deployment configuration that is used if a configuration isn't specified for either the deployment or the deployment group.

     

   

  The predefined deployment configurations including the following:

   

   
  * **CodeDeployDefault.AllAtOnce** attempts to deploy an application revision to as many instances as possible at once. The status of the overall deployment will be displayed as **Succeeded** if the application revision is deployed to one or more of the instances. The status of the overall deployment will be displayed as **Failed** if the application revision is not deployed to any of the instances. Using an example of nine instances, CodeDeployDefault.AllAtOnce will attempt to deploy to all nine instances at once. The overall deployment will succeed if deployment to even a single instance is successful; it will fail only if deployments to all nine instances fail.  
   
  * **CodeDeployDefault.HalfAtATime** deploys to up to half of the instances at a time (with fractions rounded down). The overall deployment succeeds if the application revision deploys to at least half of the instances (with fractions rounded up); otherwise, the deployment fails. For example, for nine instances, deploy to up to four instances at a time. The overall deployment succeeds if deployment to five or more instances succeed; otherwise, the deployment fails. Note that the deployment may successfully deploy to some instances, even if the overall deployment fails. 
   
  * **CodeDeployDefault.OneAtATime** deploys the application revision to only one instance at a time. For deployment groups that contain more than one instance: 

     
    * The overall deployment succeeds if the application revision deploys to all of the instances. The exception to this rule is that if deployment to the last instance fails, the overall deployment still succeeds. This is because AWS CodeDeploy allows only one instance to be taken offline at a time with the CodeDeployDefault.OneAtATime configuration. 
     
    * The overall deployment fails as soon as the application revision fails to deploy to any but the last instance. Note that the deployment may successfully deploy to some instances, even if the overall deployment fails. 
     
    * Example: For nine instances, deploy to one instance at a time. The overall deployment succeeds if the first eight instances are successfully deployed to, but it fails if deployment to any of the first eight instances fails. 
     

   

  For deployment groups that contain only one instance, the overall deployment is of course successful only if deployment to the single instance succeeds.

   
   

  

``--on-premises-instance-tag-filters`` (list)


  The on-premises instance tags to filter on.

  



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


  Information about triggers to create when the deployment group is created.

  



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


  The Amazon EC2 tags to filter on.

  



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

  

  

