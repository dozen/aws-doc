[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm list-jobs:


*********
list-jobs
*********



===========
Description
===========



Gets information about jobs.



========
Synopsis
========

::

    list-jobs
  --arn <value>
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--arn`` (string)


  The jobs' ARNs.

  

``--next-token`` (string)


  An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

jobs -> (list)

  

  Information about the jobs.

  

  (structure)

    

    Represents a device.

    

    arn -> (string)

      

      The job's ARN.

      

      

    name -> (string)

      

      The job's name.

      

      

    type -> (string)

      

      The job's type.

       

      Allowed values include the following:

       

       
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
       

      

      

    created -> (timestamp)

      

      When the job was created.

      

      

    status -> (string)

      

      The job's status.

       

      Allowed values include:

       

       
      * COMPLETED: A completed status.
       
      * PENDING: A pending status.
       
      * PROCESSING: A processing status.
       
      * RUNNING: A running status.
       
      * SCHEDULING: A scheduling status.
       

      

      

    result -> (string)

      

      The job's result.

       

      Allowed values include:

       

       
      * ERRORED: An error condition.
       
      * FAILED: A failed condition.
       
      * SKIPPED: A skipped condition.
       
      * STOPPED: A stopped condition.
       
      * PASSED: A passing condition.
       
      * PENDING: A pending condition.
       
      * WARNED: A warning condition.
       

      

      

    started -> (timestamp)

      

      The job's start time.

      

      

    stopped -> (timestamp)

      

      The job's stop time.

      

      

    counters -> (structure)

      

      The job's result counters.

      

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

      

      A message about the job's result.

      

      

    device -> (structure)

      

      Represents a device type that an app is tested against.

      

      arn -> (string)

        

        The device's ARN.

        

        

      name -> (string)

        

        The device's display name.

        

        

      manufacturer -> (string)

        

        The device's manufacturer name.

        

        

      model -> (string)

        

        The device's model name.

        

        

      formFactor -> (string)

        

        The device's form factor.

         

        Allowed values include:

         

         
        * PHONE: The phone form factor.
         
        * TABLET: The tablet form factor.
         

        

        

      platform -> (string)

        

        The device's platform.

         

        Allowed values include:

         

         
        * ANDROID: The Android platform.
         
        * IOS: The iOS platform.
         

        

        

      os -> (string)

        

        The device's operating system type.

        

        

      cpu -> (structure)

        

        Information about the device's CPU.

        

        frequency -> (string)

          

          The CPU's frequency.

          

          

        architecture -> (string)

          

          The CPU's architecture, for example x86 or ARM.

          

          

        clock -> (double)

          

          The clock speed of the device's CPU, expressed in hertz (Hz). For example, a 1.2 GHz CPU is expressed as 1200000000.

          

          

        

      resolution -> (structure)

        

        Represents the screen resolution of a device in height and width, expressed in pixels.

        

        width -> (integer)

          

          The screen resolution's width, expressed in pixels.

          

          

        height -> (integer)

          

          The screen resolution's height, expressed in pixels.

          

          

        

      heapSize -> (long)

        

        The device's heap size, expressed in bytes.

        

        

      memory -> (long)

        

        The device's total memory size, expressed in bytes.

        

        

      image -> (string)

        

        The device's image name.

        

        

      carrier -> (string)

        

        The device's carrier.

        

        

      radio -> (string)

        

        The device's radio.

        

        

      

    deviceMinutes -> (structure)

      

      Represents the total (metered or unmetered) minutes used by the job.

      

      total -> (double)

        

        When specified, represents the total minutes used by the resource to run tests.

        

        

      metered -> (double)

        

        When specified, represents only the sum of metered minutes used by the resource to run tests.

        

        

      unmetered -> (double)

        

        When specified, represents only the sum of unmetered minutes used by the resource to run tests.

        

        

      

    

  

nextToken -> (string)

  

  If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

  

  

