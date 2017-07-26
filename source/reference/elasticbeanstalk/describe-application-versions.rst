[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk describe-application-versions:


*****************************
describe-application-versions
*****************************



===========
Description
===========



Retrieve a list of application versions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/DescribeApplicationVersions>`_


========
Synopsis
========

::

    describe-application-versions
  [--application-name <value>]
  [--version-labels <value>]
  [--max-records <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  Specify an application name to show only application versions for that application.

  

``--version-labels`` (list)


  Specify a version label to show a specific application version.

  



Syntax::

  "string" "string" ...



``--max-records`` (integer)


  Specify a maximum number of application versions to paginate in the request.

  

``--next-token`` (string)


  Specify a next token to retrieve the next page in a paginated request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To view information about an application version**

The following command retrieves information about an application version labeled ``v2``::

  aws elasticbeanstalk describe-application-versions --application-name my-app --version-label "v2"

Output::

  {
      "ApplicationVersions": [
          {
              "ApplicationName": "my-app",
              "VersionLabel": "v2",
              "Description": "update cover page",
              "DateCreated": "2015-07-23T01:32:26.079Z",
              "DateUpdated": "2015-07-23T01:32:26.079Z",
              "SourceBundle": {
                  "S3Bucket": "elasticbeanstalk-us-west-2-015321684451",
                  "S3Key": "my-app/5026-stage-150723_224258.war"
              }
          },
        {
            "ApplicationName": "my-app",
            "VersionLabel": "v1",
            "Description": "initial version",
            "DateCreated": "2015-07-23T22:26:10.816Z",
            "DateUpdated": "2015-07-23T22:26:10.816Z",
            "SourceBundle": {
                "S3Bucket": "elasticbeanstalk-us-west-2-015321684451",
                "S3Key": "my-app/5026-stage-150723_222618.war"
            }
        }
      ]
  }


======
Output
======

ApplicationVersions -> (list)

  

  List of ``ApplicationVersionDescription`` objects sorted in order of creation.

  

  (structure)

    

    Describes the properties of an application version.

    

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

      

      

    

  

NextToken -> (string)

  

  For a paginated request, the token that you can pass in a subsequent request to get the next page.

  

  

