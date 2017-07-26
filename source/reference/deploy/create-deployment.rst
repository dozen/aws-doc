[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy create-deployment:


*****************
create-deployment
*****************



===========
Description
===========



Deploys an application revision through the specified deployment group.



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
  [--s3-location <value>]
  [--github-location <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The name of an existing AWS CodeDeploy application associated with the applicable IAM user or AWS account.

  

``--deployment-group-name`` (string)


  The deployment group's name.

  

``--revision`` (structure)


  The type of revision to deploy, along with information about the revision's location.

  



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


  The name of an existing deployment configuration associated with the applicable IAM user or AWS account.

   

  If not specified, the value configured in the deployment group will be used as the default. If the deployment group does not have a deployment configuration associated with it, then CodeDeployDefault.OneAtATime will be used by default.

  

``--description`` (string)


  A comment about the deployment.

  

``--ignore-application-stop-failures`` | ``--no-ignore-application-stop-failures`` (boolean)


  If set to true, then if the deployment causes the ApplicationStop deployment lifecycle event to fail to a specific instance, the deployment will not be considered to have failed to that instance at that point and will continue on to the BeforeInstall deployment lifecycle event.

   

  If set to false or not specified, then if the deployment causes the ApplicationStop deployment lifecycle event to fail to a specific instance, the deployment will stop to that instance, and the deployment to that instance will be considered to have failed.

  

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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  

