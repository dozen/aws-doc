[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk describe-application-versions:


*****************************
describe-application-versions
*****************************



===========
Description
===========



Retrieve a list of application versions stored in your AWS Elastic Beanstalk storage bucket.



========
Synopsis
========

::

    describe-application-versions
  [--application-name <value>]
  [--version-labels <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  If specified, AWS Elastic Beanstalk restricts the returned descriptions to only include ones that are associated with the specified application.

  

``--version-labels`` (list)


  If specified, restricts the returned descriptions to only include ones that have the specified version labels.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  List of ``ApplicationVersionDescription`` objects sorted by order of creation.

  

  (structure)

    

    Describes the properties of an application version. 

    

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

      

      

    

  

