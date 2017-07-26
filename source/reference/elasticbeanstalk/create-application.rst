[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk create-application:


******************
create-application
******************



===========
Description
===========



Creates an application that has one configuration template named ``default`` and no application versions. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/CreateApplication>`_


========
Synopsis
========

::

    create-application
  --application-name <value>
  [--description <value>]
  [--resource-lifecycle-config <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of the application.

   

  Constraint: This name must be unique within your account. If the specified name already exists, the action returns an ``InvalidParameterValue`` error.

  

``--description`` (string)


  Describes the application.

  

``--resource-lifecycle-config`` (structure)


  Specify an application resource lifecycle configuration to prevent your application from accumulating too many versions.

  



Shorthand Syntax::

    ServiceRole=string,VersionLifecycleConfig={MaxCountRule={Enabled=boolean,MaxCount=integer,DeleteSourceFromS3=boolean},MaxAgeRule={Enabled=boolean,MaxAgeInDays=integer,DeleteSourceFromS3=boolean}}




JSON Syntax::

  {
    "ServiceRole": "string",
    "VersionLifecycleConfig": {
      "MaxCountRule": {
        "Enabled": true|false,
        "MaxCount": integer,
        "DeleteSourceFromS3": true|false
      },
      "MaxAgeRule": {
        "Enabled": true|false,
        "MaxAgeInDays": integer,
        "DeleteSourceFromS3": true|false
      }
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a new application**

The following command creates a new application named "MyApp"::

  aws elasticbeanstalk create-application --application-name MyApp --description "my application"

The ``create-application`` command only configures the application's name and description. To upload source code for the application, create an initial version of the application using ``create-application-version``. ``create-application-version`` also has an ``auto-create-application`` option that lets you create the application and the application version in one step.

Output::

  {
    "Application": {
        "ApplicationName": "MyApp",
        "ConfigurationTemplates": [],
        "DateUpdated": "2015-02-12T18:32:21.181Z",
        "Description": "my application",
        "DateCreated": "2015-02-12T18:32:21.181Z"
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

          

          

        

      

    

  

