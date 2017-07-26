[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk create-application:


******************
create-application
******************



===========
Description
===========



Creates an application that has one configuration template named ``default`` and no application versions. 



========
Synopsis
========

::

    create-application
  --application-name <value>
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The name of the application.

   

  Constraint: This name must be unique within your account. If the specified name already exists, the action returns an ``InvalidParameterValue`` error. 

  

``--description`` (string)


  Describes the application.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

      

      

    

  

