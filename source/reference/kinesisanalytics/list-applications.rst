[ :ref:`aws <cli:aws>` . :ref:`kinesisanalytics <cli:aws kinesisanalytics>` ]

.. _cli:aws kinesisanalytics list-applications:


*****************
list-applications
*****************



===========
Description
===========



Returns a list of Amazon Kinesis Analytics applications in your account. For each application, the response includes the application name, Amazon Resource Name (ARN), and status. If the response returns the ``HasMoreApplications`` value as true, you can send another request by adding the ``ExclusiveStartApplicationName`` in the request body, and set the value of this to the last application name from the previous response. 

 

If you want detailed information about a specific application, use  describe-application .

 

This operation requires permissions to perform the ``kinesisanalytics:ListApplications`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesisanalytics-2015-08-14/ListApplications>`_


========
Synopsis
========

::

    list-applications
  [--limit <value>]
  [--exclusive-start-application-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--limit`` (integer)


  Maximum number of applications to list.

  

``--exclusive-start-application-name`` (string)


  Name of the application to start the list with. When using pagination to retrieve the list, you don't need to specify this parameter in the first request. However, in subsequent requests, you add the last application name from the previous response to get the next page of applications.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ApplicationSummaries -> (list)

  

  List of ``ApplicationSummary`` objects. 

  

  (structure)

    

    Provides application summary information, including the application Amazon Resource Name (ARN), name, and status.

    

    ApplicationName -> (string)

      

      Name of the application.

      

      

    ApplicationARN -> (string)

      

      ARN of the application.

      

      

    ApplicationStatus -> (string)

      

      Status of the application.

      

      

    

  

HasMoreApplications -> (boolean)

  

  Returns true if there are more applications to retrieve.

  

  

