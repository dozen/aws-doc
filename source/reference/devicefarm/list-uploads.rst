[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm list-uploads:


************
list-uploads
************



===========
Description
===========



Gets information about uploads, given an AWS Device Farm project ARN.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/ListUploads>`_


``list-uploads`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``uploads``


========
Synopsis
========

::

    list-uploads
  --arn <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--arn`` (string)


  The Amazon Resource Name (ARN) of the project for which you want to list uploads.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

uploads -> (list)

  

  Information about the uploads.

  

  (structure)

    

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

      

      

    

  

nextToken -> (string)

  

  If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

  

  

