[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm get-run:


*******
get-run
*******



===========
Description
===========



Gets information about a run.



========
Synopsis
========

::

    get-run
  --arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--arn`` (string)


  The run's ARN.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

run -> (structure)

  

  Represents an app on a set of devices with a specific test and configuration.

  

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

      

      

    

  

