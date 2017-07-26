[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk update-application:


******************
update-application
******************



===========
Description
===========



Updates the specified application to have the specified properties.

 

.. note::

   

  If a property (for example, ``description`` ) is not provided, the value remains unchanged. To clear these properties, specify an empty string.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/UpdateApplication>`_


========
Synopsis
========

::

    update-application
  --application-name <value>
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of the application to update. If no such application is found, ``update-application`` returns an ``InvalidParameterValue`` error. 

  

``--description`` (string)


  A new description for the application.

   

  Default: If not specified, AWS Elastic Beanstalk does not update the description.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To change an application's description**

The following command updates the description of an application named ``my-app``::

  aws elasticbeanstalk update-application --application-name my-app --description "my Elastic Beanstalk application"

Output::

  {
      "Application": {
          "ApplicationName": "my-app",
          "Description": "my Elastic Beanstalk application",
          "Versions": [
              "2fba-stage-150819_234450",
              "bf07-stage-150820_214945",
              "93f8",
              "fd7c-stage-150820_000431",
              "22a0-stage-150819_185942"
          ],
          "DateCreated": "2015-08-13T19:15:50.449Z",
          "ConfigurationTemplates": [],
          "DateUpdated": "2015-08-20T22:34:56.195Z"
      }
  }


======
Output
======

Application -> (structure)

  

  The  ApplicationDescription of the application. 

  

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

          

          

        

      

    

  

