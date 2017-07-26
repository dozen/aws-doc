[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm get-upload:


**********
get-upload
**********



===========
Description
===========



Gets information about an upload.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/GetUpload>`_


========
Synopsis
========

::

    get-upload
  --arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--arn`` (string)


  The upload's ARN.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

upload -> (structure)

  

  An app or a set of one or more tests to upload or that have been uploaded.

  

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
     
    * WEB_APP: A web appliction upload. 
     
    * EXTERNAL_DATA: An external data upload. 
     
    * APPIUM_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload. 
     
    * APPIUM_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload. 
     
    * APPIUM_PYTHON_TEST_PACKAGE: An Appium Python test package upload. 
     
    * APPIUM_WEB_JAVA_JUNIT_TEST_PACKAGE: An Appium Java JUnit test package upload. 
     
    * APPIUM_WEB_JAVA_TESTNG_TEST_PACKAGE: An Appium Java TestNG test package upload. 
     
    * APPIUM_WEB_PYTHON_TEST_PACKAGE: An Appium Python test package upload. 
     
    * CALABASH_TEST_PACKAGE: A Calabash test package upload. 
     
    * INSTRUMENTATION_TEST_PACKAGE: An instrumentation upload. 
     
    * UIAUTOMATION_TEST_PACKAGE: A uiautomation test package upload. 
     
    * UIAUTOMATOR_TEST_PACKAGE: A uiautomator test package upload. 
     
    * XCTEST_TEST_PACKAGE: An XCode test package upload. 
     
    * XCTEST_UI_TEST_PACKAGE: An XCode UI test package upload. 
     

    

    

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

    

    

  

