[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm get-run:


*******
get-run
*******



===========
Description
===========



Gets information about a run.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/GetRun>`_


========
Synopsis
========

::

    get-run
  --arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--arn`` (string)


  The run's ARN.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

run -> (structure)

  

  The run you wish to get results from.

  

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
     
    * APPIUM_WEB_JAVA_JUNIT: The Appium Java JUnit type for Web apps. 
     
    * APPIUM_WEB_JAVA_TESTNG: The Appium Java TestNG type for Web apps. 
     
    * APPIUM_WEB_PYTHON: The Appium Python type for Web apps. 
     
    * CALABASH: The Calabash type. 
     
    * INSTRUMENTATION: The Instrumentation type. 
     
    * UIAUTOMATION: The uiautomation type. 
     
    * UIAUTOMATOR: The uiautomator type. 
     
    * XCTEST: The XCode test type. 
     
    * XCTEST_UI: The XCode UI test type. 
     

    

    

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

    

    The run's result.

     

    Allowed values include:

     

     
    * PENDING: A pending condition. 
     
    * PASSED: A passing condition. 
     
    * WARNED: A warning condition. 
     
    * FAILED: A failed condition. 
     
    * SKIPPED: A skipped condition. 
     
    * ERRORED: An error condition. 
     
    * STOPPED: A stopped condition. 
     

    

    

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

    

    Specifies the billing method for a test run: ``metered`` or ``unmetered`` . If the parameter is not specified, the default value is ``metered`` .

    

    

  deviceMinutes -> (structure)

    

    Represents the total (metered or unmetered) minutes used by the test run.

    

    total -> (double)

      

      When specified, represents the total minutes used by the resource to run tests.

      

      

    metered -> (double)

      

      When specified, represents only the sum of metered minutes used by the resource to run tests.

      

      

    unmetered -> (double)

      

      When specified, represents only the sum of unmetered minutes used by the resource to run tests.

      

      

    

  networkProfile -> (structure)

    

    The network profile being used for a test run.

    

    arn -> (string)

      

      The Amazon Resource Name (ARN) of the network profile.

      

      

    name -> (string)

      

      The name of the network profile.

      

      

    description -> (string)

      

      The description of the network profile.

      

      

    type -> (string)

      

      The type of network profile. Valid values are listed below.

      

      

    uplinkBandwidthBits -> (long)

      

      The data throughput rate in bits per second, as an integer from 0 to 104857600.

      

      

    downlinkBandwidthBits -> (long)

      

      The data throughput rate in bits per second, as an integer from 0 to 104857600.

      

      

    uplinkDelayMs -> (long)

      

      Delay time for all packets to destination in milliseconds as an integer from 0 to 2000.

      

      

    downlinkDelayMs -> (long)

      

      Delay time for all packets to destination in milliseconds as an integer from 0 to 2000.

      

      

    uplinkJitterMs -> (long)

      

      Time variation in the delay of received packets in milliseconds as an integer from 0 to 2000.

      

      

    downlinkJitterMs -> (long)

      

      Time variation in the delay of received packets in milliseconds as an integer from 0 to 2000.

      

      

    uplinkLossPercent -> (integer)

      

      Proportion of transmitted packets that fail to arrive from 0 to 100 percent.

      

      

    downlinkLossPercent -> (integer)

      

      Proportion of received packets that fail to arrive from 0 to 100 percent.

      

      

    

  

