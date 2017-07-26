[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk describe-applications:


*********************
describe-applications
*********************



===========
Description
===========



Returns the descriptions of existing applications.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/DescribeApplications>`_


========
Synopsis
========

::

    describe-applications
  [--application-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-names`` (list)


  If specified, AWS Elastic Beanstalk restricts the returned descriptions to only include those with the specified names.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To view a list of applications**

The following command retrieves information about applications in the current region::

  aws elasticbeanstalk describe-applications

Output::

  {
      "Applications": [
          {
              "ApplicationName": "ruby",
              "ConfigurationTemplates": [],
              "DateUpdated": "2015-08-13T21:05:44.376Z",
              "Versions": [
                  "Sample Application"
              ],
              "DateCreated": "2015-08-13T21:05:44.376Z"
          },
          {
              "ApplicationName": "pythonsample",
              "Description": "Application created from the EB CLI using \"eb init\"",
              "Versions": [
                  "Sample Application"
              ],
              "DateCreated": "2015-08-13T19:05:43.637Z",
              "ConfigurationTemplates": [],
              "DateUpdated": "2015-08-13T19:05:43.637Z"
          },
          {
              "ApplicationName": "nodejs-example",
              "ConfigurationTemplates": [],
              "DateUpdated": "2015-08-06T17:50:02.486Z",
              "Versions": [
                  "add elasticache",
                  "First Release"
              ],
              "DateCreated": "2015-08-06T17:50:02.486Z"
          }
      ]
  }


======
Output
======

Applications -> (list)

  

  This parameter contains a list of  ApplicationDescription .

  

  (structure)

    

    Describes the properties of an application.

    

    ApplicationName -> (string)

      

      The name of the application.

      

      

    Description -> (string)

      

      User-defined description of the application.

      

      

    DateCreated -> (timestamp)

      

      The date when the application was created.

      

      

    DateUpdated -> (timestamp)

      

      The date when the application was last modified.

      

      

    Versions -> (list)

      

      The names of the versions for this application.

      

      (string)

        

        

      

    ConfigurationTemplates -> (list)

      

      The names of the configuration templates associated with this application.

      

      (string)

        

        

      

    ResourceLifecycleConfig -> (structure)

      

      The lifecycle settings for the application.

      

      ServiceRole -> (string)

        

        The ARN of an IAM service role that Elastic Beanstalk has permission to assume.

        

        

      VersionLifecycleConfig -> (structure)

        

        The application version lifecycle configuration.

        

        MaxCountRule -> (structure)

          

          Specify a max count rule to restrict the number of application versions that are retained for an application.

          

          Enabled -> (boolean)

            

            Specify ``true`` to apply the rule, or ``false`` to disable it.

            

            

          MaxCount -> (integer)

            

            Specify the maximum number of application versions to retain.

            

            

          DeleteSourceFromS3 -> (boolean)

            

            Set to ``true`` to delete a version's source bundle from Amazon S3 when Elastic Beanstalk deletes the application version.

            

            

          

        MaxAgeRule -> (structure)

          

          Specify a max age rule to restrict the length of time that application versions are retained for an application.

          

          Enabled -> (boolean)

            

            Specify ``true`` to apply the rule, or ``false`` to disable it.

            

            

          MaxAgeInDays -> (integer)

            

            Specify the number of days to retain an application versions.

            

            

          DeleteSourceFromS3 -> (boolean)

            

            Set to ``true`` to delete a version's source bundle from Amazon S3 when Elastic Beanstalk deletes the application version.

            

            

          

        

      

    

  

