[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy push:


****
push
****



===========
Description
===========

Bundles and uploads to Amazon Simple Storage Service (Amazon S3) an application revision, which is an archive file that contains deployable content and an accompanying Application Specification file (AppSpec file). If the upload is successful, a message is returned that describes how to call the create-deployment command to deploy the application revision from Amazon S3 to target Amazon Elastic Compute Cloud (Amazon EC2) instances.



========
Synopsis
========

::

    push
  --application-name <app-name>
  --s3-location s3://<bucket>/<key>
  [--ignore-hidden-files | --no-ignore-hidden-files]
  [--source <path>]
  [--description <description>]




=======
Options
=======

``--application-name`` (string)
Required. The name of the AWS CodeDeploy application to be associated with the application revision.

``--s3-location`` (string)
Required. Information about the location of the application revision to be uploaded to Amazon S3. You must specify both a bucket and a key that represent the Amazon S3 bucket name and the object key name. Use the format s3://\/\

``--ignore-hidden-files`` | ``--no-ignore-hidden-files`` (boolean)
Optional. Set the --ignore-hidden-files flag to not bundle and upload hidden files to Amazon S3; otherwise, set the --no-ignore-hidden-files flag (the default) to bundle and upload hidden files to Amazon S3.

``--source`` (string)
Optional. The location of the deployable content and the accompanying AppSpec file on the development machine to be bundled and uploaded to Amazon S3. If not specified, the current directory is used.

``--description`` (string)
Optional. A comment that summarizes the application revision. If not specified, the default string "Uploaded by AWS CLI 'time' UTC" is used, where 'time' is the current system time in Coordinated Universal Time (UTC).



========
Examples
========

**To bundle and deploy an AWS CodeDeploy compatible application revision to Amazon S3**

This example bundles and deploys an application revision to Amazon S3 and then associates the application revision with the specified application.

Use the output of the push command to create a deployment that uses the uploaded application revision.

Command::

  aws deploy push --application-name WordPress_App --description "This is my deployment" --ignore-hidden-files --s3-location s3://CodeDeployDemoBucket/WordPressApp.zip --source /tmp/MyLocalDeploymentFolder/

Output::

  To deploy with this revision, run: 
  aws deploy create-deployment --application-name WordPress_App --deployment-config-name <deployment-config-name> --deployment-group-name <deployment-group-name> --s3-location bucket=CodeDeployDemoBucket,key=WordPressApp.zip,bundleType=zip,eTag="cecc9b8a08eac650a6e71fdb88EXAMPLE",version=LFsJAUd_2J4VWXfvKtvi79L8EXAMPLE