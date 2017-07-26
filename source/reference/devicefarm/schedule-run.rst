[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm schedule-run:


************
schedule-run
************



===========
Description
===========



Schedules a run.



========
Synopsis
========

::

    schedule-run
  --project-arn <value>
  [--app-arn <value>]
  --device-pool-arn <value>
  [--name <value>]
  --test <value>
  [--configuration <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--project-arn`` (string)


  The ARN of the project for the run to be scheduled.

  

``--app-arn`` (string)


  The ARN of the app to schedule a run.

  

``--device-pool-arn`` (string)


  The ARN of the device pool for the run to be scheduled.

  

``--name`` (string)


  The name for the run to be scheduled.

  

``--test`` (structure)


  Information about the test for the run to be scheduled.

  



Shorthand Syntax::

    type=string,testPackageArn=string,filter=string,parameters={KeyName1=string,KeyName2=string}




JSON Syntax::

  {
    "type": "BUILTIN_FUZZ"|"BUILTIN_EXPLORER"|"APPIUM_JAVA_JUNIT"|"APPIUM_JAVA_TESTNG"|"APPIUM_PYTHON"|"APPIUM_WEB_JAVA_JUNIT"|"APPIUM_WEB_JAVA_TESTNG"|"APPIUM_WEB_PYTHON"|"CALABASH"|"INSTRUMENTATION"|"UIAUTOMATION"|"UIAUTOMATOR"|"XCTEST",
    "testPackageArn": "string",
    "filter": "string",
    "parameters": {"string": "string"
      ...}
  }



``--configuration`` (structure)


  Information about the settings for the run to be scheduled.

  



Shorthand Syntax::

    extraDataPackageArn=string,networkProfileArn=string,locale=string,location={latitude=double,longitude=double},radios={wifi=boolean,bluetooth=boolean,nfc=boolean,gps=boolean},auxiliaryApps=string,string,billingMethod=string




JSON Syntax::

  {
    "extraDataPackageArn": "string",
    "networkProfileArn": "string",
    "locale": "string",
    "location": {
      "latitude": double,
      "longitude": double
    },
    "radios": {
      "wifi": true|false,
      "bluetooth": true|false,
      "nfc": true|false,
      "gps": true|false
    },
    "auxiliaryApps": ["string", ...],
    "billingMethod": "METERED"|"UNMETERED"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

run -> (structure)

  

  Information about the scheduled run.

  

  arn -> (string)

    

    The run's ARN.

    

    

  name -> (string)

    

    The run's name.

    

    

  type -> (string)

    

    The run's type.

     

    Must be one of the following values:

     

     
    * BUILTIN_FUZZ: The built-in fuzz type.
     
    * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time.
     
    * APPIUM_JAVA_JUNIT: The Appium Java JUnit type.
     
    * APPIUM_JAVA_TESTNG: The Appium Java TestNG type.
     
    * APPIUM_PYTHON: The Appium Python type.
     
    * CALABASH: The Calabash type.
     
    * INSTRUMENTATION: The Instrumentation type.
     
    * UIAUTOMATION: The uiautomation type.
     
    * UIAUTOMATOR: The uiautomator type.
     
    * XCTEST: The XCode test type.
     
    * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps.
     
    * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps.
     
    * APPIUM_WEB_PYTHON: The Appium Python type for Web apps.
     

    

    

  platform -> (string)

    

    The run's platform.

     

    Allowed values include:

     

     
    * ANDROID: The Android platform.
     
    * IOS: The iOS platform.
     

    

    

  created -> (timestamp)

    

    When the run was created.

    

    

  status -> (string)

    

    The run's status.

     

    Allowed values include:

     

     
    * COMPLETED: A completed status.
     
    * PENDING: A pending status.
     
    * PROCESSING: A processing status.
     
    * RUNNING: A running status.
     
    * SCHEDULING: A scheduling status.
     

    

    

  result -> (string)

    

    The run's result.

     

    Allowed values include:

     

     
    * ERRORED: An error condition.
     
    * FAILED: A failed condition.
     
    * SKIPPED: A skipped condition.
     
    * STOPPED: A stopped condition.
     
    * PASSED: A passing condition.
     
    * PENDING: A pending condition.
     
    * WARNED: A warning condition.
     

    

    

  started -> (timestamp)

    

    The run's start time.

    

    

  stopped -> (timestamp)

    

    The run's stop time.

    

    

  counters -> (structure)

    

    The run's result counters.

    

    total -> (integer)

      

      The total number of entities.

      

      

    passed -> (integer)

      

      The number of passed entities.

      

      

    failed -> (integer)

      

      The number of failed entities.

      

      

    warned -> (integer)

      

      The number of warned entities.

      

      

    errored -> (integer)

      

      The number of errored entities.

      

      

    stopped -> (integer)

      

      The number of stopped entities.

      

      

    skipped -> (integer)

      

      The number of skipped entities.

      

      

    

  message -> (string)

    

    A message about the run's result.

    

    

  totalJobs -> (integer)

    

    The total number of jobs for the run.

    

    

  completedJobs -> (integer)

    

    The total number of completed jobs.

    

    

  billingMethod -> (string)

    

    Specifies the billing method for a test run: ``metered`` or ``unmetered`` . If the parameter is not specified, the default value is ``unmetered`` .

    

    

  deviceMinutes -> (structure)

    

    Represents the total (metered or unmetered) minutes used by the test run.

    

    total -> (double)

      

      When specified, represents the total minutes used by the resource to run tests.

      

      

    metered -> (double)

      

      When specified, represents only the sum of metered minutes used by the resource to run tests.

      

      

    unmetered -> (double)

      

      When specified, represents only the sum of unmetered minutes used by the resource to run tests.

      

      

    

  

