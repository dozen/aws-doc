[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy batch-get-application-revisions:


*******************************
batch-get-application-revisions
*******************************



===========
Description
===========



Gets information about one or more application revisions.



========
Synopsis
========

::

    batch-get-application-revisions
  --application-name <value>
  --revisions <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The name of an existing AWS CodeDeploy application to get revision information about.

  

``--revisions`` (list)


  Information to get about the application revisions, including revision type and location.

  



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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

applicationName -> (string)

  

  The name of the application that corresponds to the revisions.

  

  

errorMessage -> (string)

  

  Information about errors that may have occurred during the API call.

  

  

revisions -> (list)

  

  Additional information about the revisions, including the revision type and location.

  

  (structure)

    

    Information about an application revision.

    

    revisionLocation -> (structure)

      

      Information about an application revision's location.

      

      revisionType -> (string)

        

        The application revision's type:

         

         
        * S3: An application revision stored in Amazon S3.
         
        * GitHub: An application revision stored in GitHub.
         

        

        

      s3Location -> (structure)

        

        Information about the location of application artifacts that are stored in Amazon S3.

        

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

        

        Information about the location of application artifacts that are stored in GitHub.

        

        repository -> (string)

          

          The GitHub account and repository pair that stores a reference to the commit that represents the bundled artifacts for the application revision. 

           

          Specified as account/repository.

          

          

        commitId -> (string)

          

          The SHA1 commit ID of the GitHub commit that represents the bundled artifacts for the application revision.

          

          

        

      

    genericRevisionInfo -> (structure)

      

      Information about an application revision.

      

      description -> (string)

        

        A comment about the revision.

        

        

      deploymentGroups -> (list)

        

        The deployment groups where this is the current target revision.

        

        (string)

          

          

        

      firstUsedTime -> (timestamp)

        

        When the revision was first used by AWS CodeDeploy.

        

        

      lastUsedTime -> (timestamp)

        

        When the revision was last used by AWS CodeDeploy.

        

        

      registerTime -> (timestamp)

        

        When the revision was registered with AWS CodeDeploy.

        

        

      

    

  

