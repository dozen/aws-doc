[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm get-device-pool-compatibility:


*****************************
get-device-pool-compatibility
*****************************



===========
Description
===========



Gets information about compatibility with a device pool.



========
Synopsis
========

::

    get-device-pool-compatibility
  --device-pool-arn <value>
  [--app-arn <value>]
  [--test-type <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--device-pool-arn`` (string)


  The device pool's ARN.

  

``--app-arn`` (string)


  The ARN of the app that is associated with the specified device pool.

  

``--test-type`` (string)


  The test type for the specified device pool.

   

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
   

  

  Possible values:

  
  *   ``BUILTIN_FUZZ``

  
  *   ``BUILTIN_EXPLORER``

  
  *   ``APPIUM_JAVA_JUNIT``

  
  *   ``APPIUM_JAVA_TESTNG``

  
  *   ``APPIUM_PYTHON``

  
  *   ``APPIUM_WEB_JAVA_JUNIT``

  
  *   ``APPIUM_WEB_JAVA_TESTNG``

  
  *   ``APPIUM_WEB_PYTHON``

  
  *   ``CALABASH``

  
  *   ``INSTRUMENTATION``

  
  *   ``UIAUTOMATION``

  
  *   ``UIAUTOMATOR``

  
  *   ``XCTEST``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

compatibleDevices -> (list)

  

  Information about compatible devices.

  

  (structure)

    

    Represents a device pool compatibility result.

    

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

        

        

      

    compatible -> (boolean)

      

      Whether the result was compatible with the device pool.

      

      

    incompatibilityMessages -> (list)

      

      Information about the compatibility.

      

      (structure)

        

        Represents information about incompatibility.

        

        message -> (string)

          

          A message about the incompatibility.

          

          

        type -> (string)

          

          The type of incompatibility.

           

          Allowed values include:

           

           
          * ARN: The ARN.
           
          * FORM_FACTOR: The form factor (for example, phone or tablet).
           
          * MANUFACTURER: The manufacturer.
           
          * PLATFORM: The platform (for example, Android or iOS).
           

          

          

        

      

    

  

incompatibleDevices -> (list)

  

  Information about incompatible devices.

  

  (structure)

    

    Represents a device pool compatibility result.

    

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

        

        

      

    compatible -> (boolean)

      

      Whether the result was compatible with the device pool.

      

      

    incompatibilityMessages -> (list)

      

      Information about the compatibility.

      

      (structure)

        

        Represents information about incompatibility.

        

        message -> (string)

          

          A message about the incompatibility.

          

          

        type -> (string)

          

          The type of incompatibility.

           

          Allowed values include:

           

           
          * ARN: The ARN.
           
          * FORM_FACTOR: The form factor (for example, phone or tablet).
           
          * MANUFACTURER: The manufacturer.
           
          * PLATFORM: The platform (for example, Android or iOS).
           

          

          

        

      

    

  

