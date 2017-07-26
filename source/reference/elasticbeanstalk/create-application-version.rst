[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk create-application-version:


**************************
create-application-version
**************************



===========
Description
===========



Creates an application version for the specified application.

 

.. note::

  Once you create an application version with a specified Amazon S3 bucket and key location, you cannot change that Amazon S3 location. If you change the Amazon S3 location, you receive an exception when you attempt to launch an environment from the application version. 



========
Synopsis
========

::

    create-application-version
  --application-name <value>
  --version-label <value>
  [--description <value>]
  [--source-bundle <value>]
  [--auto-create-application | --no-auto-create-application]
  [--process | --no-process]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The name of the application. If no application is found with this name, and ``no-auto-create-application`` is ``false`` , returns an ``InvalidParameterValue`` error. 

  

``--version-label`` (string)


  A label identifying this version.

   

  Constraint: Must be unique per application. If an application version already exists with this label for the specified application, AWS Elastic Beanstalk returns an ``InvalidParameterValue`` error. 

  

``--description`` (string)


  Describes this version.

  

``--source-bundle`` (structure)


  The Amazon S3 bucket and key that identify the location of the source bundle for this version. 

   

  If data found at the Amazon S3 location exceeds the maximum allowed source bundle size, AWS Elastic Beanstalk returns an ``InvalidParameterValue`` error. The maximum size allowed is 512 MB. 

   

  Default: If not specified, AWS Elastic Beanstalk uses a sample application. If only partially specified (for example, a bucket is provided but not the key) or if no data is found at the Amazon S3 location, AWS Elastic Beanstalk returns an ``InvalidParameterCombination`` error. 

  



Shorthand Syntax::

    S3Bucket=string,S3Key=string




JSON Syntax::

  {
    "S3Bucket": "string",
    "S3Key": "string"
  }



``--auto-create-application`` | ``--no-auto-create-application`` (boolean)


  Determines how the system behaves if the specified application for this version does not already exist: 

   

   
  * ``true`` : Automatically creates the specified application for this release if it does not already exist. 
   
  * ``false`` : Throws an ``InvalidParameterValue`` if the specified application for this release does not already exist. 
   

   

  Default: ``false``  

   

  Valid Values: ``true`` | ``false``  

  

``--process`` | ``--no-process`` (boolean)


  Preprocesses and validates the environment manifest and configuration files in the source bundle. Validating configuration files can identify issues prior to deploying the application version to an environment.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

    

    The name of the application associated with this release.

    

    

  Description -> (string)

    

    The description of this application version.

    

    

  VersionLabel -> (string)

    

    A label uniquely identifying the version for the associated application. 

    

    

  SourceBundle -> (structure)

    

    The location where the source bundle is located for this version. 

    

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

    

    

  

