[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk create-application-version:


**************************
create-application-version
**************************



===========
Description
===========



Creates an application version for the specified application. You can create an application version from a source bundle in Amazon S3, a commit in AWS CodeCommit, or the output of an AWS CodeBuild build as follows:

 

Specify a commit in an AWS CodeCommit repository with ``source-build-information`` .

 

Specify a build in an AWS CodeBuild with ``source-build-information`` and ``build-configuration`` .

 

Specify a source bundle in S3 with ``SourceBundle``  

 

Omit both ``source-build-information`` and ``SourceBundle`` to use the default sample application.

 

.. note::

   

  Once you create an application version with a specified Amazon S3 bucket and key location, you cannot change that Amazon S3 location. If you change the Amazon S3 location, you receive an exception when you attempt to launch an environment from the application version.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/CreateApplicationVersion>`_


========
Synopsis
========

::

    create-application-version
  --application-name <value>
  --version-label <value>
  [--description <value>]
  [--source-build-information <value>]
  [--source-bundle <value>]
  [--build-configuration <value>]
  [--auto-create-application | --no-auto-create-application]
  [--process | --no-process]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of the application. If no application is found with this name, and ``auto-create-application`` is ``false`` , returns an ``InvalidParameterValue`` error. 

  

``--version-label`` (string)


  A label identifying this version.

   

  Constraint: Must be unique per application. If an application version already exists with this label for the specified application, AWS Elastic Beanstalk returns an ``InvalidParameterValue`` error. 

  

``--description`` (string)


  Describes this version.

  

``--source-build-information`` (structure)


  Specify a commit in an AWS CodeCommit Git repository to use as the source code for the application version.

  



Shorthand Syntax::

    SourceType=string,SourceRepository=string,SourceLocation=string




JSON Syntax::

  {
    "SourceType": "Git"|"Zip",
    "SourceRepository": "CodeCommit"|"S3",
    "SourceLocation": "string"
  }



``--source-bundle`` (structure)


  The Amazon S3 bucket and key that identify the location of the source bundle for this version.

   

  .. note::

     

    The Amazon S3 bucket must be in the same region as the environment.

     

   

  Specify a source bundle in S3 or a commit in an AWS CodeCommit repository (with ``source-build-information`` ), but not both. If neither ``SourceBundle`` nor ``source-build-information`` are provided, Elastic Beanstalk uses a sample application.

  



Shorthand Syntax::

    S3Bucket=string,S3Key=string




JSON Syntax::

  {
    "S3Bucket": "string",
    "S3Key": "string"
  }



``--build-configuration`` (structure)


  Settings for an AWS CodeBuild build.

  



Shorthand Syntax::

    ArtifactName=string,CodeBuildServiceRole=string,ComputeType=string,Image=string,TimeoutInMinutes=integer




JSON Syntax::

  {
    "ArtifactName": "string",
    "CodeBuildServiceRole": "string",
    "ComputeType": "BUILD_GENERAL1_SMALL"|"BUILD_GENERAL1_MEDIUM"|"BUILD_GENERAL1_LARGE",
    "Image": "string",
    "TimeoutInMinutes": integer
  }



``--auto-create-application`` | ``--no-auto-create-application`` (boolean)


  Set to ``true`` to create an application with the specified name if it doesn't already exist.

  

``--process`` | ``--no-process`` (boolean)


  Preprocesses and validates the environment manifest and configuration files in the source bundle. Validating configuration files can identify issues prior to deploying the application version to an environment.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a new application version**

The following command creates a new version, "v1" of an application named "MyApp"::

  aws elasticbeanstalk create-application-version --application-name MyApp --version-label v1 --description MyAppv1 --source-bundle S3Bucket="my-bucket",S3Key="sample.war" --auto-create-application

The application will be created automatically if it does not already exist, due to the auto-create-application option. The source bundle is a .war file stored in an s3 bucket named "my-bucket" that contains the Apache Tomcat sample application.

Output::

  {
    "ApplicationVersion": {
        "ApplicationName": "MyApp",
        "VersionLabel": "v1",
        "Description": "MyAppv1",
        "DateCreated": "2015-02-03T23:01:25.412Z",
        "DateUpdated": "2015-02-03T23:01:25.412Z",
        "SourceBundle": {
            "S3Bucket": "my-bucket",
            "S3Key": "sample.war"
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

    

    

  

