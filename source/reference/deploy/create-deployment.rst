[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy create-deployment:


*****************
create-deployment
*****************



===========
Description
===========



Deploys an application revision through the specified deployment group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/CreateDeployment>`_


========
Synopsis
========

::

    create-deployment
  --application-name <value>
  [--deployment-group-name <value>]
  [--revision <value>]
  [--deployment-config-name <value>]
  [--description <value>]
  [--ignore-application-stop-failures | --no-ignore-application-stop-failures]
  [--target-instances <value>]
  [--auto-rollback-configuration <value>]
  [--update-outdated-instances-only | --no-update-outdated-instances-only]
  [--file-exists-behavior <value>]
  [--s3-location <value>]
  [--github-location <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

  

``--deployment-group-name`` (string)


  The name of the deployment group.

  

``--revision`` (structure)


  The type and location of the revision to deploy.

  



Shorthand Syntax::

    revisionType=string,s3Location={bucket=string,key=string,bundleType=string,version=string,eTag=string},gitHubLocation={repository=string,commitId=string}




JSON Syntax::

  {
    "revisionType": "S3"|"GitHub",
    "s3Location": {
      "bucket": "string",
      "key": "string",
      "bundleType": "tar"|"tgz"|"zip",
      "version": "string",
      "eTag": "string"
    },
    "gitHubLocation": {
      "repository": "string",
      "commitId": "string"
    }
  }



``--deployment-config-name`` (string)


  The name of a deployment configuration associated with the applicable IAM user or AWS account.

   

  If not specified, the value configured in the deployment group will be used as the default. If the deployment group does not have a deployment configuration associated with it, then CodeDeployDefault.OneAtATime will be used by default.

  

``--description`` (string)


  A comment about the deployment.

  

``--ignore-application-stop-failures`` | ``--no-ignore-application-stop-failures`` (boolean)


  If set to true, then if the deployment causes the ApplicationStop deployment lifecycle event to an instance to fail, the deployment to that instance will not be considered to have failed at that point and will continue on to the BeforeInstall deployment lifecycle event.

   

  If set to false or not specified, then if the deployment causes the ApplicationStop deployment lifecycle event to fail to an instance, the deployment to that instance will stop, and the deployment to that instance will be considered to have failed.

  

``--target-instances`` (structure)


  Information about the instances that will belong to the replacement environment in a blue/green deployment.

  



Shorthand Syntax::

    tagFilters=[{Key=string,Value=string,Type=string},{Key=string,Value=string,Type=string}],autoScalingGroups=string,string




JSON Syntax::

  {
    "tagFilters": [
      {
        "Key": "string",
        "Value": "string",
        "Type": "KEY_ONLY"|"VALUE_ONLY"|"KEY_AND_VALUE"
      }
      ...
    ],
    "autoScalingGroups": ["string", ...]
  }



``--auto-rollback-configuration`` (structure)


  Configuration information for an automatic rollback that is added when a deployment is created.

  



Shorthand Syntax::

    enabled=boolean,events=string,string




JSON Syntax::

  {
    "enabled": true|false,
    "events": ["DEPLOYMENT_FAILURE"|"DEPLOYMENT_STOP_ON_ALARM"|"DEPLOYMENT_STOP_ON_REQUEST", ...]
  }



``--update-outdated-instances-only`` | ``--no-update-outdated-instances-only`` (boolean)


  Indicates whether to deploy to all instances or only to instances that are not running the latest application revision.

  

``--file-exists-behavior`` (string)


  Information about how AWS CodeDeploy handles files that already exist in a deployment target location but weren't part of the previous successful deployment.

   

  The fileExistsBehavior parameter takes any of the following values:

   

   
  * DISALLOW: The deployment fails. This is also the default behavior if no option is specified. 
   
  * OVERWRITE: The version of the file from the application revision currently being deployed replaces the version already on the instance. 
   
  * RETAIN: The version of the file already on the instance is kept and used as part of the new deployment. 
   

  

  Possible values:

  
  *   ``DISALLOW``

  
  *   ``OVERWRITE``

  
  *   ``RETAIN``

  

  

``--s3-location`` (structure)
Information about the location of the application revision in Amazon S3. You must specify the bucket, the key, and bundleType. Optionally, you can also specify an eTag and version.



Shorthand Syntax::

    bundleType=string,eTag=string,bucket=string,version=string,key=string




JSON Syntax::

  {
    "bundleType": "tar"|"tgz"|"zip",
    "eTag": "string",
    "bucket": "string",
    "version": "string",
    "key": "string"
  }



``--github-location`` (structure)
Information about the location of the application revision in GitHub. You must specify the repository and commit ID that references the application revision. For the repository, use the format GitHub-account/repository-name or GitHub-org/repository-name. For the commit ID, use the SHA1 Git commit reference.



Shorthand Syntax::

    commitId=string,repository=string




JSON Syntax::

  {
    "commitId": "string",
    "repository": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a deployment**

This example creates a deployment and associates it with the user's AWS account.

Command::

  aws deploy create-deployment --application-name WordPress_App --deployment-config-name CodeDeployDefault.OneAtATime --deployment-group-name WordPress_DG --description "My demo deployment" --s3-location bucket=CodeDeployDemoBucket,bundleType=zip,eTag=dd56cfd59d434b8e768f9d77fEXAMPLE,key=WordPressApp.zip

Output::

  {
      "deploymentId": "d-N65YI7Gex"
  }

======
Output
======

deploymentId -> (string)

  

  A unique deployment ID.

  

  

