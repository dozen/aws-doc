[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk update-application-version:


**************************
update-application-version
**************************



===========
Description
===========



Updates the specified application version to have the specified properties.

 

.. note::

   

  If a property (for example, ``description`` ) is not provided, the value remains unchanged. To clear properties, specify an empty string.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/UpdateApplicationVersion>`_


========
Synopsis
========

::

    update-application-version
  --application-name <value>
  --version-label <value>
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of the application associated with this version.

   

  If no application is found with this name, ``update-application`` returns an ``InvalidParameterValue`` error.

  

``--version-label`` (string)


  The name of the version to update.

   

  If no application version is found with this label, ``update-application`` returns an ``InvalidParameterValue`` error. 

  

``--description`` (string)


  A new description for this version.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To change an application version's description**

The following command updates the description of an application version named ``22a0-stage-150819_185942``::

  aws elasticbeanstalk update-application-version --version-label 22a0-stage-150819_185942 --application-name my-app --description "new description"

Output::

  {
      "ApplicationVersion": {
          "ApplicationName": "my-app",
          "VersionLabel": "22a0-stage-150819_185942",
          "Description": "new description",
          "DateCreated": "2015-08-19T18:59:17.646Z",
          "DateUpdated": "2015-08-20T22:53:28.871Z",
          "SourceBundle": {
              "S3Bucket": "elasticbeanstalk-us-west-2-0123456789012",
              "S3Key": "my-app/22a0-stage-150819_185942.war"
          }
      }
  }

======
Output
======

ApplicationVersion -> (structure)

  

  The  ApplicationVersionDescription of the application version. 

  

  ApplicationName -> (string)

    

    The name of the application to which the application version belongs.

    

    

  Description -> (string)

    

    The description of the application version.

    

    

  VersionLabel -> (string)

    

    A unique identifier for the application version.

    

    

  SourceBuildInformation -> (structure)

    

    If the version's source code was retrieved from AWS CodeCommit, the location of the source code for the application version.

    

    SourceType -> (string)

      

      The type of repository.

       

       
      * ``Git``   
       
      * ``Zip``   
       

      

      

    SourceRepository -> (string)

      

      Location where the repository is stored.

       

       
      * ``CodeCommit``   
       
      * ``S3``   
       

      

      

    SourceLocation -> (string)

      

      The location of the source code, as a formatted string, depending on the value of ``SourceRepository``  

       

       
      * For ``CodeCommit`` , the format is the repository name and commit ID, separated by a forward slash. For example, ``my-git-repo/265cfa0cf6af46153527f55d6503ec030551f57a`` . 
       
      * For ``S3`` , the format is the S3 bucket name and object key, separated by a forward slash. For example, ``my-s3-bucket/Folders/my-source-file`` . 
       

      

      

    

  BuildArn -> (string)

    

    Reference to the artifact from the AWS CodeBuild build.

    

    

  SourceBundle -> (structure)

    

    The storage location of the application version's source bundle in Amazon S3.

    

    S3Bucket -> (string)

      

      The Amazon S3 bucket where the data is located.

      

      

    S3Key -> (string)

      

      The Amazon S3 key where the data is located.

      

      

    

  DateCreated -> (timestamp)

    

    The creation date of the application version.

    

    

  DateUpdated -> (timestamp)

    

    The last modified date of the application version.

    

    

  Status -> (string)

    

    The processing status of the application version.

    

    

  

