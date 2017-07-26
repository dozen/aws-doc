[ :ref:`aws <cli:aws>` . :ref:`kinesisanalytics <cli:aws kinesisanalytics>` ]

.. _cli:aws kinesisanalytics create-application:


******************
create-application
******************



===========
Description
===========



Creates an Amazon Kinesis Analytics application. You can configure each application with one streaming source as input, application code to process the input, and up to five streaming destinations where you want Amazon Kinesis Analytics to write the output data from your application. For an overview, see `How it Works <http://docs.aws.amazon.com/kinesisanalytics/latest/dev/how-it-works.html>`_ . 

 

In the input configuration, you map the streaming source to an in-application stream, which you can think of as a constantly updating table. In the mapping, you must provide a schema for the in-application stream and map each data column in the in-application stream to a data element in the streaming source.

 

Your application code is one or more SQL statements that read input data, transform it, and generate output. Your application code can create one or more SQL artifacts like SQL streams or pumps.

 

In the output configuration, you can configure the application to write data from in-application streams created in your applications to up to five streaming destinations.

 

To read data from your source stream or write data to destination streams, Amazon Kinesis Analytics needs your permissions. You grant these permissions by creating IAM roles. This operation requires permissions to perform the ``kinesisanalytics:CreateApplication`` action. 

 

For introductory exercises to create an Amazon Kinesis Analytics application, see `Getting Started <http://docs.aws.amazon.com/kinesisanalytics/latest/dev/getting-started.html>`_ . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesisanalytics-2015-08-14/CreateApplication>`_


========
Synopsis
========

::

    create-application
  --application-name <value>
  [--application-description <value>]
  [--inputs <value>]
  [--outputs <value>]
  [--cloud-watch-logging-options <value>]
  [--application-code <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  Name of your Amazon Kinesis Analytics application (for example, ``sample-app`` ).

  

``--application-description`` (string)


  Summary description of the application.

  

``--inputs`` (list)


  Use this parameter to configure the application input.

   

  You can configure your application to receive input from a single streaming source. In this configuration, you map this streaming source to an in-application stream that is created. Your application code can then query the in-application stream like a table (you can think of it as a constantly updating table).

   

  For the streaming source, you provide its Amazon Resource Name (ARN) and format of data on the stream (for example, JSON, CSV, etc). You also must provide an IAM role that Amazon Kinesis Analytics can assume to read this stream on your behalf.

   

  To create the in-application stream, you need to specify a schema to transform your data into a schematized version used in SQL. In the schema, you provide the necessary mapping of the data elements in the streaming source to record columns in the in-app stream.

  



JSON Syntax::

  [
    {
      "NamePrefix": "string",
      "KinesisStreamsInput": {
        "ResourceARN": "string",
        "RoleARN": "string"
      },
      "KinesisFirehoseInput": {
        "ResourceARN": "string",
        "RoleARN": "string"
      },
      "InputParallelism": {
        "Count": integer
      },
      "InputSchema": {
        "RecordFormat": {
          "RecordFormatType": "JSON"|"CSV",
          "MappingParameters": {
            "JSONMappingParameters": {
              "RecordRowPath": "string"
            },
            "CSVMappingParameters": {
              "RecordRowDelimiter": "string",
              "RecordColumnDelimiter": "string"
            }
          }
        },
        "RecordEncoding": "string",
        "RecordColumns": [
          {
            "Name": "string",
            "Mapping": "string",
            "SqlType": "string"
          }
          ...
        ]
      }
    }
    ...
  ]



``--outputs`` (list)


  You can configure application output to write data from any of the in-application streams to up to five destinations.

   

  These destinations can be Amazon Kinesis streams, Amazon Kinesis Firehose delivery streams, or both.

   

  In the configuration, you specify the in-application stream name, the destination stream Amazon Resource Name (ARN), and the format to use when writing data. You must also provide an IAM role that Amazon Kinesis Analytics can assume to write to the destination stream on your behalf.

   

  In the output configuration, you also provide the output stream Amazon Resource Name (ARN) and the format of data in the stream (for example, JSON, CSV). You also must provide an IAM role that Amazon Kinesis Analytics can assume to write to this stream on your behalf.

  



Shorthand Syntax::

    Name=string,KinesisStreamsOutput={ResourceARN=string,RoleARN=string},KinesisFirehoseOutput={ResourceARN=string,RoleARN=string},DestinationSchema={RecordFormatType=string} ...




JSON Syntax::

  [
    {
      "Name": "string",
      "KinesisStreamsOutput": {
        "ResourceARN": "string",
        "RoleARN": "string"
      },
      "KinesisFirehoseOutput": {
        "ResourceARN": "string",
        "RoleARN": "string"
      },
      "DestinationSchema": {
        "RecordFormatType": "JSON"|"CSV"
      }
    }
    ...
  ]



``--cloud-watch-logging-options`` (list)


  Use this parameter to configure a CloudWatch log stream to monitor application configuration errors. For more information, see `Monitoring Configuration Errors <http://docs.aws.amazon.com/kinesisanalytics/latest/dev/cloudwatch-monitor-configuration.html>`_ .

  



Shorthand Syntax::

    LogStreamARN=string,RoleARN=string ...




JSON Syntax::

  [
    {
      "LogStreamARN": "string",
      "RoleARN": "string"
    }
    ...
  ]



``--application-code`` (string)


  One or more SQL statements that read input data, transform it, and generate output. For example, you can write a SQL statement that reads data from one in-application stream, generates a running average of the number of advertisement clicks by vendor, and insert resulting rows in another in-application stream using pumps. For more inforamtion about the typical pattern, see `Application Code <http://docs.aws.amazon.com/kinesisanalytics/latest/dev/how-it-works-app-code.html>`_ . 

   

  You can provide such series of SQL statements, where output of one statement can be used as the input for the next statement. You store intermediate results by creating in-application streams and pumps.

   

  Note that the application code must create the streams with names specified in the ``outputs`` . For example, if your ``outputs`` defines output streams named ``ExampleOutputStream1`` and ``ExampleOutputStream2`` , then your application code must create these streams. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ApplicationSummary -> (structure)

  

  In response to your ``create-application`` request, Amazon Kinesis Analytics returns a response with a summary of the application it created, including the application Amazon Resource Name (ARN), name, and status.

  

  ApplicationName -> (string)

    

    Name of the application.

    

    

  ApplicationARN -> (string)

    

    ARN of the application.

    

    

  ApplicationStatus -> (string)

    

    Status of the application.

    

    

  

