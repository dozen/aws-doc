[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm create-upload:


*************
create-upload
*************



===========
Description
===========



Uploads an app or test scripts.



========
Synopsis
========

::

    create-upload
  --project-arn <value>
  --name <value>
  --type <value>
  [--content-type <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--project-arn`` (string)


  The ARN of the project for the upload.

  

``--name`` (string)


  The upload's file name.

  

``--type`` (string)


  The upload's upload type.

   

  Must be one of the following values:

   

   
  * ANDROID_APP: An Android upload.
   
  * IOS_APP: An iOS upload.
   
  * EXTERNAL_DATA: An external data upload.
   
  * APPIUM_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload.
   
  * APPIUM_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload.
   
  * APPIUM_PYTHON_TEST_PACKAGE: An Appium Python test package upload.
   
  * CALABASH_TEST_PACKAGE: A Calabash test package upload.
   
  * INSTRUMENTATION_TEST_PACKAGE: An instrumentation upload.
   
  * UIAUTOMATOR_TEST_PACKAGE: A uiautomator test package upload.
   
  * XCTEST_TEST_PACKAGE: An XCode test package upload.
   
  * APPIUM_WEB_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload.
   
  * APPIUM_WEB_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload.
   
  * APPIUM_WEB_PYTHON_TEST_PACKAGE: An Appium Python test package upload.
   

   

  **Note** If you call ``create-upload`` with ``WEB_APP`` specified, AWS Device Farm throws an ``ArgumentException`` error.

  

  Possible values:

  
  *   ``ANDROID_APP``

  
  *   ``IOS_APP``

  
  *   ``WEB_APP``

  
  *   ``EXTERNAL_DATA``

  
  *   ``APPIUM_JAVA_JUNIT_TEST_PACKAGE``

  
  *   ``APPIUM_JAVA_TESTNG_TEST_PACKAGE``

  
  *   ``APPIUM_PYTHON_TEST_PACKAGE``

  
  *   ``APPIUM_WEB_JAVA_JUNIT_TEST_PACKAGE``

  
  *   ``APPIUM_WEB_JAVA_TESTNG_TEST_PACKAGE``

  
  *   ``APPIUM_WEB_PYTHON_TEST_PACKAGE``

  
  *   ``CALABASH_TEST_PACKAGE``

  
  *   ``INSTRUMENTATION_TEST_PACKAGE``

  
  *   ``UIAUTOMATION_TEST_PACKAGE``

  
  *   ``UIAUTOMATOR_TEST_PACKAGE``

  
  *   ``XCTEST_TEST_PACKAGE``

  

  

``--content-type`` (string)


  The upload's content type (for example, "application/octet-stream").

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

upload -> (structure)

  

  The newly created upload.

  

  arn -> (string)

    

    The upload's ARN.

    

    

  name -> (string)

    

    The upload's file name.

    

    

  created -> (timestamp)

    

    When the upload was created.

    

    

  type -> (string)

    

    The upload's type.

     

    Must be one of the following values:

     

     
    * ANDROID_APP: An Android upload.
     
    * IOS_APP: An iOS upload.
     
    * EXTERNAL_DATA: An external data upload.
     
    * APPIUM_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload.
     
    * APPIUM_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload.
     
    * APPIUM_PYTHON_TEST_PACKAGE: An Appium Python test package upload.
     
    * CALABASH_TEST_PACKAGE: A Calabash test package upload.
     
    * INSTRUMENTATION_TEST_PACKAGE: An instrumentation upload.
     
    * UIAUTOMATOR_TEST_PACKAGE: A uiautomator test package upload.
     
    * XCTEST_TEST_PACKAGE: An XCode test package upload.
     
    * APPIUM_WEB_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload.
     
    * APPIUM_WEB_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload.
     
    * APPIUM_WEB_PYTHON_TEST_PACKAGE: An Appium Python test package upload.
     

    

    

  status -> (string)

    

    The upload's status.

     

    Must be one of the following values:

     

     
    * FAILED: A failed status.
     
    * INITIALIZED: An initialized status.
     
    * PROCESSING: A processing status.
     
    * SUCCEEDED: A succeeded status.
     

    

    

  url -> (string)

    

    The pre-signed Amazon S3 URL that was used to store a file through a corresponding PUT request.

    

    

  metadata -> (string)

    

    The upload's metadata. For example, for Android, this contains information that is parsed from the manifest and is displayed in the AWS Device Farm console after the associated app is uploaded.

    

    

  contentType -> (string)

    

    The upload's content type (for example, "application/octet-stream").

    

    

  message -> (string)

    

    A message about the upload's result.

    

    

  

