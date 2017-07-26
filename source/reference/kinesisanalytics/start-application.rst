[ :ref:`aws <cli:aws>` . :ref:`kinesisanalytics <cli:aws kinesisanalytics>` ]

.. _cli:aws kinesisanalytics start-application:


*****************
start-application
*****************



===========
Description
===========



Starts the specified Amazon Kinesis Analytics application. After creating an application, you must exclusively call this operation to start your application.

 

After the application starts, it begins consuming the input data, processes it, and writes the output to the configured destination.

 

The application status must be ``READY`` for you to start an application. You can get the application status in the console or using the  describe-application operation.

 

After you start the application, you can stop the application from processing the input by calling the  stop-application operation.

 

This operation requires permissions to perform the ``kinesisanalytics:StartApplication`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesisanalytics-2015-08-14/StartApplication>`_


========
Synopsis
========

::

    start-application
  --application-name <value>
  --input-configurations <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  Name of the application.

  

``--input-configurations`` (list)


  Identifies the specific input, by ID, that the application starts consuming. Amazon Kinesis Analytics starts reading the streaming source associated with the input. You can also specify where in the streaming source you want Amazon Kinesis Analytics to start reading.

  



Shorthand Syntax::

    Id=string,InputStartingPositionConfiguration={InputStartingPosition=string} ...




JSON Syntax::

  [
    {
      "Id": "string",
      "InputStartingPositionConfiguration": {
        "InputStartingPosition": "NOW"|"TRIM_HORIZON"|"LAST_STOPPED_POINT"
      }
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

