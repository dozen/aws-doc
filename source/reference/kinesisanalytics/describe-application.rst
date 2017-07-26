[ :ref:`aws <cli:aws>` . :ref:`kinesisanalytics <cli:aws kinesisanalytics>` ]

.. _cli:aws kinesisanalytics describe-application:


********************
describe-application
********************



===========
Description
===========



Returns information about a specific Amazon Kinesis Analytics application.

 

If you want to retrieve a list of all applications in your account, use the  list-applications operation.

 

This operation requires permissions to perform the ``kinesisanalytics:DescribeApplication`` action. You can use ``describe-application`` to get the current application versionId, which you need to call other operations such as ``Update`` . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesisanalytics-2015-08-14/DescribeApplication>`_


========
Synopsis
========

::

    describe-application
  --application-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  Name of the application.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ApplicationDetail -> (structure)

  

  Provides a description of the application, such as the application Amazon Resource Name (ARN), status, latest version, and input and output configuration details.

  

  ApplicationName -> (string)

    

    Name of the application.

    

    

  ApplicationDescription -> (string)

    

    Description of the application.

    

    

  ApplicationARN -> (string)

    

    ARN of the application.

    

    

  ApplicationStatus -> (string)

    

    Status of the application.

    

    

  CreateTimestamp -> (timestamp)

    

    Timestamp when the application version was created.

    

    

  LastUpdateTimestamp -> (timestamp)

    

    Timestamp when the application was last updated.

    

    

  InputDescriptions -> (list)

    

    Describes the application input configuration. For more information, see `Configuring Application Input <http://docs.aws.amazon.com/kinesisanalytics/latest/dev/how-it-works-input.html>`_ . 

    

    (structure)

      

      Describes the application input configuration. For more information, see `Configuring Application Input <http://docs.aws.amazon.com/kinesisanalytics/latest/dev/how-it-works-input.html>`_ . 

      

      InputId -> (string)

        

        Input ID associated with the application input. This is the ID that Amazon Kinesis Analytics assigns to each input configuration you add to your application. 

        

        

      NamePrefix -> (string)

        

        In-application name prefix.

        

        

      InAppStreamNames -> (list)

        

        Returns the in-application stream names that are mapped to the stream source.

        

        (string)

          

          

        

      KinesisStreamsInputDescription -> (structure)

        

        If an Amazon Kinesis stream is configured as streaming source, provides Amazon Kinesis stream's ARN and an IAM role that enables Amazon Kinesis Analytics to access the stream on your behalf.

        

        ResourceARN -> (string)

          

          Amazon Resource Name (ARN) of the Amazon Kinesis stream.

          

          

        RoleARN -> (string)

          

          ARN of the IAM role that Amazon Kinesis Analytics can assume to access the stream.

          

          

        

      KinesisFirehoseInputDescription -> (structure)

        

        If an Amazon Kinesis Firehose delivery stream is configured as a streaming source, provides the Firehose delivery stream's Amazon Resource Name (ARN) and an IAM role that enables Amazon Kinesis Analytics to access the stream on your behalf.

        

        ResourceARN -> (string)

          

          Amazon Resource Name (ARN) of the Amazon Kinesis Firehose delivery stream.

          

          

        RoleARN -> (string)

          

          ARN of the IAM role that Amazon Kinesis Analytics assumes to access the stream.

          

          

        

      InputSchema -> (structure)

        

        Describes the format of the data in the streaming source, and how each data element maps to corresponding columns created in the in-application stream.

        

        RecordFormat -> (structure)

          

          Specifies the format of the records on the streaming source.

          

          RecordFormatType -> (string)

            

            The type of record format.

            

            

          MappingParameters -> (structure)

            

            When configuring application input at the time of creating or updating an application, provides additional mapping information specific to the record format (such as JSON, CSV, or record fields delimited by some delimiter) on the streaming source.

            

            JSONMappingParameters -> (structure)

              

              Provides additional mapping information when JSON is the record format on the streaming source.

              

              RecordRowPath -> (string)

                

                Path to the top-level parent that contains the records.

                 

                For example, consider the following JSON record:

                 

                In the ``RecordRowPath`` , ``"$"`` refers to the root and path ``"$.vehicle.Model"`` refers to the specific ``"Model"`` key in the JSON.

                

                

              

            CSVMappingParameters -> (structure)

              

              Provides additional mapping information when the record format uses delimiters (for example, CSV).

              

              RecordRowDelimiter -> (string)

                

                Row delimiter. For example, in a CSV format, *'\n'* is the typical row delimiter.

                

                

              RecordColumnDelimiter -> (string)

                

                Column delimiter. For example, in a CSV format, a comma (",") is the typical column delimiter.

                

                

              

            

          

        RecordEncoding -> (string)

          

          Specifies the encoding of the records in the streaming source. For example, UTF-8.

          

          

        RecordColumns -> (list)

          

          A list of ``RecordColumn`` objects.

          

          (structure)

            

            Describes the mapping of each data element in the streaming source to the corresponding column in the in-application stream.

             

            Also used to describe the format of the reference data source.

            

            Name -> (string)

              

              Name of the column created in the in-application input stream or reference table.

              

              

            Mapping -> (string)

              

              Reference to the data element in the streaming input of the reference data source.

              

              

            SqlType -> (string)

              

              Type of column created in the in-application input stream or reference table.

              

              

            

          

        

      InputParallelism -> (structure)

        

        Describes the configured parallelism (number of in-application streams mapped to the streaming source).

        

        Count -> (integer)

          

          Number of in-application streams to create. For more information, see `Limits <http://docs.aws.amazon.com/kinesisanalytics/latest/dev/limits.html>`_ . 

          

          

        

      InputStartingPositionConfiguration -> (structure)

        

        Point at which the application is configured to read from the input stream.

        

        InputStartingPosition -> (string)

          

          The starting position on the stream.

           

           
          * ``NOW`` - Start reading just after the most recent record in the stream, start at the request timestamp that the customer issued. 
           
          * ``TRIM_HORIZON`` - Start reading at the last untrimmed record in the stream, which is the oldest record available in the stream. This option is not available for an Amazon Kinesis Firehose delivery stream. 
           
          * ``LAST_STOPPED_POINT`` - Resume reading from where the application last stopped reading. 
           

          

          

        

      

    

  OutputDescriptions -> (list)

    

    Describes the application output configuration. For more information, see `Configuring Application Output <http://docs.aws.amazon.com/kinesisanalytics/latest/dev/how-it-works-output.html>`_ . 

    

    (structure)

      

      Describes the application output configuration, which includes the in-application stream name and the destination where the stream data is written. The destination can be an Amazon Kinesis stream or an Amazon Kinesis Firehose delivery stream. 

      

      OutputId -> (string)

        

        A unique identifier for the output configuration.

        

        

      Name -> (string)

        

        Name of the in-application stream configured as output.

        

        

      KinesisStreamsOutputDescription -> (structure)

        

        Describes Amazon Kinesis stream configured as the destination where output is written.

        

        ResourceARN -> (string)

          

          Amazon Resource Name (ARN) of the Amazon Kinesis stream.

          

          

        RoleARN -> (string)

          

          ARN of the IAM role that Amazon Kinesis Analytics can assume to access the stream.

          

          

        

      KinesisFirehoseOutputDescription -> (structure)

        

        Describes the Amazon Kinesis Firehose delivery stream configured as the destination where output is written.

        

        ResourceARN -> (string)

          

          Amazon Resource Name (ARN) of the Amazon Kinesis Firehose delivery stream.

          

          

        RoleARN -> (string)

          

          ARN of the IAM role that Amazon Kinesis Analytics can assume to access the stream.

          

          

        

      DestinationSchema -> (structure)

        

        Data format used for writing data to the destination.

        

        RecordFormatType -> (string)

          

          Specifies the format of the records on the output stream.

          

          

        

      

    

  ReferenceDataSourceDescriptions -> (list)

    

    Describes reference data sources configured for the application. For more information, see `Configuring Application Input <http://docs.aws.amazon.com/kinesisanalytics/latest/dev/how-it-works-input.html>`_ . 

    

    (structure)

      

      Describes the reference data source configured for an application.

      

      ReferenceId -> (string)

        

        ID of the reference data source. This is the ID that Amazon Kinesis Analytics assigns when you add the reference data source to your application using the  add-application-reference-data-source operation.

        

        

      TableName -> (string)

        

        The in-application table name created by the specific reference data source configuration.

        

        

      S3ReferenceDataSourceDescription -> (structure)

        

        Provides the S3 bucket name, the object key name that contains the reference data. It also provides the Amazon Resource Name (ARN) of the IAM role that Amazon Kinesis Analytics can assume to read the Amazon S3 object and populate the in-application reference table.

        

        BucketARN -> (string)

          

          Amazon Resource Name (ARN) of the S3 bucket.

          

          

        FileKey -> (string)

          

          Amazon S3 object key name.

          

          

        ReferenceRoleARN -> (string)

          

          ARN of the IAM role that Amazon Kinesis Analytics can assume to read the Amazon S3 object on your behalf to populate the in-application reference table.

          

          

        

      ReferenceSchema -> (structure)

        

        Describes the format of the data in the streaming source, and how each data element maps to corresponding columns created in the in-application stream.

        

        RecordFormat -> (structure)

          

          Specifies the format of the records on the streaming source.

          

          RecordFormatType -> (string)

            

            The type of record format.

            

            

          MappingParameters -> (structure)

            

            When configuring application input at the time of creating or updating an application, provides additional mapping information specific to the record format (such as JSON, CSV, or record fields delimited by some delimiter) on the streaming source.

            

            JSONMappingParameters -> (structure)

              

              Provides additional mapping information when JSON is the record format on the streaming source.

              

              RecordRowPath -> (string)

                

                Path to the top-level parent that contains the records.

                 

                For example, consider the following JSON record:

                 

                In the ``RecordRowPath`` , ``"$"`` refers to the root and path ``"$.vehicle.Model"`` refers to the specific ``"Model"`` key in the JSON.

                

                

              

            CSVMappingParameters -> (structure)

              

              Provides additional mapping information when the record format uses delimiters (for example, CSV).

              

              RecordRowDelimiter -> (string)

                

                Row delimiter. For example, in a CSV format, *'\n'* is the typical row delimiter.

                

                

              RecordColumnDelimiter -> (string)

                

                Column delimiter. For example, in a CSV format, a comma (",") is the typical column delimiter.

                

                

              

            

          

        RecordEncoding -> (string)

          

          Specifies the encoding of the records in the streaming source. For example, UTF-8.

          

          

        RecordColumns -> (list)

          

          A list of ``RecordColumn`` objects.

          

          (structure)

            

            Describes the mapping of each data element in the streaming source to the corresponding column in the in-application stream.

             

            Also used to describe the format of the reference data source.

            

            Name -> (string)

              

              Name of the column created in the in-application input stream or reference table.

              

              

            Mapping -> (string)

              

              Reference to the data element in the streaming input of the reference data source.

              

              

            SqlType -> (string)

              

              Type of column created in the in-application input stream or reference table.

              

              

            

          

        

      

    

  CloudWatchLoggingOptionDescriptions -> (list)

    

    Describes the CloudWatch log streams configured to receive application messages. For more information about using CloudWatch log streams with Amazon Kinesis Analytics applications, see `Monitoring Configuration Errors <http://docs.aws.amazon.com/kinesisanalytics/latest/dev/cloudwatch-monitor-configuration.html>`_ . 

    

    (structure)

      

      Description of the CloudWatch logging option.

      

      CloudWatchLoggingOptionId -> (string)

        

        ID of the CloudWatch logging option description.

        

        

      LogStreamARN -> (string)

        

        ARN of the CloudWatch log to receive application messages.

        

        

      RoleARN -> (string)

        

        IAM ARN of the role to use to send application messages. Note: To write application messages to CloudWatch, the IAM role used must have the ``PutLogEvents`` policy action enabled.

        

        

      

    

  ApplicationCode -> (string)

    

    Returns the application code that you provided to perform data analysis on any of the in-application streams in your application.

    

    

  ApplicationVersionId -> (long)

    

    Provides the current application version.

    

    

  

