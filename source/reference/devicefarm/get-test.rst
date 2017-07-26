[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm get-test:


********
get-test
********



===========
Description
===========



Gets information about a test.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/GetTest>`_


========
Synopsis
========

::

    get-test
  --arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--arn`` (string)


  The test's ARN.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

test -> (structure)

  

  A test condition that is evaluated.

  

  arn -> (string)

    

    The test's ARN.

    

    

  name -> (string)

    

    The test's name.

    

    

  type -> (string)

    

    The test's type.

     

    Must be one of the following values:

     

     
    * BUILTIN_FUZZ: The built-in fuzz type. 
     
    * BUILTIN_EXPLORER: For Android, an app explorer that will traverse an Android app, interacting with it and capturing screenshots at the same time. 
     
    * APPIUM_JAVA_JUNIT: The Appium Java JUnit type. 
     
    * APPIUM_JAVA_TESTNG: The Appium Java TestNG type. 
     
    * APPIUM_PYTHON: The Appium Python type. 
     
    * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps. 
     
    * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps. 
     
    * APPIUM_WEB_PYTHON: The Appium Python type for Web apps. 
     
    * CALABASH: The Calabash type. 
     
    * INSTRUMENTATION: The Instrumentation type. 
     
    * UIAUTOMATION: The uiautomation type. 
     
    * UIAUTOMATOR: The uiautomator type. 
     
    * XCTEST: The XCode test type. 
     
    * XCTEST_UI: The XCode UI test type. 
     

    

    

  created -> (timestamp)

    

    When the test was created.

    

    

  status -> (string)

    

    The test's status.

     

    Allowed values include:

     

     
    * PENDING: A pending status. 
     
    * PENDING_CONCURRENCY: A pending concurrency status. 
     
    * PENDING_DEVICE: A pending device status. 
     
    * PROCESSING: A processing status. 
     
    * SCHEDULING: A scheduling status. 
     
    * PREPARING: A preparing status. 
     
    * RUNNING: A running status. 
     
    * COMPLETED: A completed status. 
     
    * STOPPING: A stopping status. 
     

    

    

  result -> (string)

    

    The test's result.

     

    Allowed values include:

     

     
    * PENDING: A pending condition. 
     
    * PASSED: A passing condition. 
     
    * WARNED: A warning condition. 
     
    * FAILED: A failed condition. 
     
    * SKIPPED: A skipped condition. 
     
    * ERRORED: An error condition. 
     
    * STOPPED: A stopped condition. 
     

    

    

  started -> (timestamp)

    

    The test's start time.

    

    

  stopped -> (timestamp)

    

    The test's stop time.

    

    

  counters -> (structure)

    

    The test's result counters.

    

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

    

    A message about the test's result.

    

    

  deviceMinutes -> (structure)

    

    Represents the total (metered or unmetered) minutes used by the test.

    

    total -> (double)

      

      When specified, represents the total minutes used by the resource to run tests.

      

      

    metered -> (double)

      

      When specified, represents only the sum of metered minutes used by the resource to run tests.

      

      

    unmetered -> (double)

      

      When specified, represents only the sum of unmetered minutes used by the resource to run tests.

      

      

    

  

