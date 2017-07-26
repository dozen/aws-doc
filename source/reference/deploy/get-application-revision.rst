[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy get-application-revision:


************************
get-application-revision
************************



===========
Description
===========



Gets information about an application revision.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/GetApplicationRevision>`_


========
Synopsis
========

::

    get-application-revision
  --application-name <value>
  [--revision <value>]
  [--s3-location <value>]
  [--github-location <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of the application that corresponds to the revision.

  

``--revision`` (structure)


  Information about the application revision to get, including type and location.

  



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

**To get information about an application revision**

This example displays information about an application revision that is associated with the specified application.

Command::

  aws deploy get-application-revision --application-name WordPress_App --s3-location bucket=CodeDeployDemoBucket,bundleType=zip,eTag=dd56cfd59d434b8e768f9d77fEXAMPLE,key=WordPressApp.zip

Output::

  {
      "applicationName": "WordPress_App",
      "revisionInfo": {
          "description": "Application revision registered by Deployment ID: d-N65I7GEX",
          "registerTime": 1411076520.009,
          "deploymentGroups": "WordPress_DG",
          "lastUsedTime": 1411076520.009,
          "firstUsedTime": 1411076520.009
      },
      "revision": {
	      "revisionType": "S3",
		  "s3Location": {
		    "bundleType": "zip",
            "eTag": "dd56cfd59d434b8e768f9d77fEXAMPLE",
            "bucket": "CodeDeployDemoBucket",
            "key": "WordPressApp.zip"
	      }
      }
  }

======
Output
======

applicationName -> (string)

  

  The name of the application that corresponds to the revision.

  

  

revision -> (structure)

  

  Additional information about the revision, including type and location.

  

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

      

      

    

  

revisionInfo -> (structure)

  

  General information about the revision.

  

  description -> (string)

    

    A comment about the revision.

    

    

  deploymentGroups -> (list)

    

    The deployment groups for which this is the current target revision.

    

    (string)

      

      

    

  firstUsedTime -> (timestamp)

    

    When the revision was first used by AWS CodeDeploy.

    

    

  lastUsedTime -> (timestamp)

    

    When the revision was last used by AWS CodeDeploy.

    

    

  registerTime -> (timestamp)

    

    When the revision was registered with AWS CodeDeploy.

    

    

  

