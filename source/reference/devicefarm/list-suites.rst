[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm list-suites:


***********
list-suites
***********



===========
Description
===========



Gets information about suites.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/ListSuites>`_


``list-suites`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``suites``


========
Synopsis
========

::

    list-suites
  --arn <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--arn`` (string)


  The suites' ARNs.

  

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

suites -> (list)

  

  Information about the suites.

  

  (structure)

    

    Represents a collection of one or more tests.

    

    arn -> (string)

      

      The suite's ARN.

      

      

    name -> (string)

      

      The suite's name.

      

      

    type -> (string)

      

      The suite's type.

       

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

      

      When the suite was created.

      

      

    status -> (string)

      

      The suite's status.

       

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

      

      The suite's result.

       

      Allowed values include:

       

       
      * PENDING: A pending condition. 
       
      * PASSED: A passing condition. 
       
      * WARNED: A warning condition. 
       
      * FAILED: A failed condition. 
       
      * SKIPPED: A skipped condition. 
       
      * ERRORED: An error condition. 
       
      * STOPPED: A stopped condition. 
       

      

      

    started -> (timestamp)

      

      The suite's start time.

      

      

    stopped -> (timestamp)

      

      The suite's stop time.

      

      

    counters -> (structure)

      

      The suite's result counters.

      

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

      

      A message about the suite's result.

      

      

    deviceMinutes -> (structure)

      

      Represents the total (metered or unmetered) minutes used by the test suite.

      

      total -> (double)

        

        When specified, represents the total minutes used by the resource to run tests.

        

        

      metered -> (double)

        

        When specified, represents only the sum of metered minutes used by the resource to run tests.

        

        

      unmetered -> (double)

        

        When specified, represents only the sum of unmetered minutes used by the resource to run tests.

        

        

      

    

  

nextToken -> (string)

  

  If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

  

  

