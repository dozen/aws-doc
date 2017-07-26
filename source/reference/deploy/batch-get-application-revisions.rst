[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy batch-get-application-revisions:


*******************************
batch-get-application-revisions
*******************************



===========
Description
===========



Gets information about one or more application revisions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/BatchGetApplicationRevisions>`_


========
Synopsis
========

::

    batch-get-application-revisions
  --application-name <value>
  --revisions <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of an AWS CodeDeploy application about which to get revision information.

  

``--revisions`` (list)


  Information to get about the application revisions, including type and location.

  



Shorthand Syntax::

    revisionType=string,s3Location={bucket=string,key=string,bundleType=string,version=string,eTag=string},gitHubLocation={repository=string,commitId=string} ...




JSON Syntax::

  [
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
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

applicationName -> (string)

  

  The name of the application that corresponds to the revisions.

  

  

errorMessage -> (string)

  

  Information about errors that may have occurred during the API call.

  

  

revisions -> (list)

  

  Additional information about the revisions, including the type and location.

  

  (structure)

    

    Information about an application revision.

    

    revisionLocation -> (structure)

      

      Information about the location and type of an application revision.

      

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

          

          

        

      

    genericRevisionInfo -> (structure)

      

      Information about an application revision, including usage details and associated deployment groups.

      

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

        

        

      

    

  

