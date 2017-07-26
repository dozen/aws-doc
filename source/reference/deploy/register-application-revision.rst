[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy register-application-revision:


*****************************
register-application-revision
*****************************



===========
Description
===========



Registers with AWS CodeDeploy a revision for the specified application.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/RegisterApplicationRevision>`_


========
Synopsis
========

::

    register-application-revision
  --application-name <value>
  [--description <value>]
  [--revision <value>]
  [--s3-location <value>]
  [--github-location <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

  

``--description`` (string)


  A comment about the revision.

  

``--revision`` (structure)


  Information about the application revision to register, including type and location.

  



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

**To register information about an already-uploaded application revision**

This example registers information about an already-uploaded application revision in Amazon S3 with AWS CodeDeploy.

Command::

  aws deploy register-application-revision --application-name WordPress_App --description "Revised WordPress application" --s3-location bucket=CodeDeployDemoBucket,key=RevisedWordPressApp.zip,bundleType=zip,eTag=cecc9b8a08eac650a6e71fdb88EXAMPLE

Output::

  None.

======
Output
======

None