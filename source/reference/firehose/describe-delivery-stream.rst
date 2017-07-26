[ :ref:`aws <cli:aws>` . :ref:`firehose <cli:aws firehose>` ]

.. _cli:aws firehose describe-delivery-stream:


************************
describe-delivery-stream
************************



===========
Description
===========



Describes the specified delivery stream and gets the status. For example, after your delivery stream is created, call  describe-delivery-stream to see if the delivery stream is ``ACTIVE`` and therefore ready for data to be sent to it.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/firehose-2015-08-04/DescribeDeliveryStream>`_


========
Synopsis
========

::

    describe-delivery-stream
  --delivery-stream-name <value>
  [--limit <value>]
  [--exclusive-start-destination-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--delivery-stream-name`` (string)


  The name of the delivery stream.

  

``--limit`` (integer)


  The limit on the number of destinations to return. Currently, you can have one destination per delivery stream.

  

``--exclusive-start-destination-id`` (string)


  The ID of the destination to start returning the destination information. Currently Firehose supports one destination per delivery stream.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DeliveryStreamDescription -> (structure)

  

  Information about the delivery stream.

  

  DeliveryStreamName -> (string)

    

    The name of the delivery stream.

    

    

  DeliveryStreamARN -> (string)

    

    The Amazon Resource Name (ARN) of the delivery stream.

    

    

  DeliveryStreamStatus -> (string)

    

    The status of the delivery stream.

    

    

  VersionId -> (string)

    

    Each time the destination is updated for a delivery stream, the version ID is changed, and the current version ID is required when updating the destination. This is so that the service knows it is applying the changes to the correct version of the delivery stream.

    

    

  CreateTimestamp -> (timestamp)

    

    The date and time that the delivery stream was created.

    

    

  LastUpdateTimestamp -> (timestamp)

    

    The date and time that the delivery stream was last updated.

    

    

  Destinations -> (list)

    

    The destinations.

    

    (structure)

      

      Describes the destination for a delivery stream.

      

      DestinationId -> (string)

        

        The ID of the destination.

        

        

      S3DestinationDescription -> (structure)

        

        [Deprecated] The destination in Amazon S3.

        

        RoleARN -> (string)

          

          The ARN of the AWS credentials.

          

          

        BucketARN -> (string)

          

          The ARN of the S3 bucket.

          

          

        Prefix -> (string)

          

          The "YYYY/MM/DD/HH" time format prefix is automatically used for delivered S3 files. You can specify an extra prefix to be added in front of the time format prefix. Note that if the prefix ends with a slash, it appears as a folder in the S3 bucket. For more information, see `Amazon S3 Object Name Format <http://docs.aws.amazon.com/firehose/latest/dev/basic-deliver.html>`_ in the *Amazon Kinesis Firehose Developer Guide* .

          

          

        BufferingHints -> (structure)

          

          The buffering option. If no value is specified, **BufferingHints** object default values are used.

          

          SizeInMBs -> (integer)

            

            Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

             

            We recommend setting this parameter to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec, the value should be 10 MB or higher.

            

            

          IntervalInSeconds -> (integer)

            

            Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300.

            

            

          

        CompressionFormat -> (string)

          

          The compression format. If no value is specified, the default is ``UNCOMPRESSED`` .

          

          

        EncryptionConfiguration -> (structure)

          

          The encryption configuration. If no value is specified, the default is no encryption.

          

          NoEncryptionConfig -> (string)

            

            Specifically override existing encryption information to ensure no encryption is used.

            

            

          KMSEncryptionConfig -> (structure)

            

            The encryption key.

            

            AWSKMSKeyARN -> (string)

              

              The ARN of the encryption key. Must belong to the same region as the destination Amazon S3 bucket.

              

              

            

          

        CloudWatchLoggingOptions -> (structure)

          

          The CloudWatch logging options for your delivery stream.

          

          Enabled -> (boolean)

            

            Enables or disables CloudWatch logging.

            

            

          LogGroupName -> (string)

            

            The CloudWatch group name for logging. This value is required if CloudWatch logging is enabled.

            

            

          LogStreamName -> (string)

            

            The CloudWatch log stream name for logging. This value is required if CloudWatch logging is enabled.

            

            

          

        

      ExtendedS3DestinationDescription -> (structure)

        

        The destination in Amazon S3.

        

        RoleARN -> (string)

          

          The ARN of the AWS credentials.

          

          

        BucketARN -> (string)

          

          The ARN of the S3 bucket.

          

          

        Prefix -> (string)

          

          The "YYYY/MM/DD/HH" time format prefix is automatically used for delivered S3 files. You can specify an extra prefix to be added in front of the time format prefix. Note that if the prefix ends with a slash, it appears as a folder in the S3 bucket. For more information, see `Amazon S3 Object Name Format <http://docs.aws.amazon.com/firehose/latest/dev/basic-deliver.html>`_ in the *Amazon Kinesis Firehose Developer Guide* .

          

          

        BufferingHints -> (structure)

          

          The buffering option.

          

          SizeInMBs -> (integer)

            

            Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

             

            We recommend setting this parameter to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec, the value should be 10 MB or higher.

            

            

          IntervalInSeconds -> (integer)

            

            Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300.

            

            

          

        CompressionFormat -> (string)

          

          The compression format. If no value is specified, the default is ``UNCOMPRESSED`` .

          

          

        EncryptionConfiguration -> (structure)

          

          The encryption configuration. If no value is specified, the default is no encryption.

          

          NoEncryptionConfig -> (string)

            

            Specifically override existing encryption information to ensure no encryption is used.

            

            

          KMSEncryptionConfig -> (structure)

            

            The encryption key.

            

            AWSKMSKeyARN -> (string)

              

              The ARN of the encryption key. Must belong to the same region as the destination Amazon S3 bucket.

              

              

            

          

        CloudWatchLoggingOptions -> (structure)

          

          The CloudWatch logging options for your delivery stream.

          

          Enabled -> (boolean)

            

            Enables or disables CloudWatch logging.

            

            

          LogGroupName -> (string)

            

            The CloudWatch group name for logging. This value is required if CloudWatch logging is enabled.

            

            

          LogStreamName -> (string)

            

            The CloudWatch log stream name for logging. This value is required if CloudWatch logging is enabled.

            

            

          

        ProcessingConfiguration -> (structure)

          

          The data processing configuration.

          

          Enabled -> (boolean)

            

            Enables or disables data processing.

            

            

          Processors -> (list)

            

            The data processors.

            

            (structure)

              

              Describes a data processor.

              

              Type -> (string)

                

                The type of processor.

                

                

              Parameters -> (list)

                

                The processor parameters.

                

                (structure)

                  

                  Describes the processor parameter.

                  

                  ParameterName -> (string)

                    

                    The name of the parameter.

                    

                    

                  ParameterValue -> (string)

                    

                    The parameter value.

                    

                    

                  

                

              

            

          

        S3BackupMode -> (string)

          

          The Amazon S3 backup mode.

          

          

        S3BackupDescription -> (structure)

          

          The configuration for backup in Amazon S3.

          

          RoleARN -> (string)

            

            The ARN of the AWS credentials.

            

            

          BucketARN -> (string)

            

            The ARN of the S3 bucket.

            

            

          Prefix -> (string)

            

            The "YYYY/MM/DD/HH" time format prefix is automatically used for delivered S3 files. You can specify an extra prefix to be added in front of the time format prefix. Note that if the prefix ends with a slash, it appears as a folder in the S3 bucket. For more information, see `Amazon S3 Object Name Format <http://docs.aws.amazon.com/firehose/latest/dev/basic-deliver.html>`_ in the *Amazon Kinesis Firehose Developer Guide* .

            

            

          BufferingHints -> (structure)

            

            The buffering option. If no value is specified, **BufferingHints** object default values are used.

            

            SizeInMBs -> (integer)

              

              Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

               

              We recommend setting this parameter to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec, the value should be 10 MB or higher.

              

              

            IntervalInSeconds -> (integer)

              

              Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300.

              

              

            

          CompressionFormat -> (string)

            

            The compression format. If no value is specified, the default is ``UNCOMPRESSED`` .

            

            

          EncryptionConfiguration -> (structure)

            

            The encryption configuration. If no value is specified, the default is no encryption.

            

            NoEncryptionConfig -> (string)

              

              Specifically override existing encryption information to ensure no encryption is used.

              

              

            KMSEncryptionConfig -> (structure)

              

              The encryption key.

              

              AWSKMSKeyARN -> (string)

                

                The ARN of the encryption key. Must belong to the same region as the destination Amazon S3 bucket.

                

                

              

            

          CloudWatchLoggingOptions -> (structure)

            

            The CloudWatch logging options for your delivery stream.

            

            Enabled -> (boolean)

              

              Enables or disables CloudWatch logging.

              

              

            LogGroupName -> (string)

              

              The CloudWatch group name for logging. This value is required if CloudWatch logging is enabled.

              

              

            LogStreamName -> (string)

              

              The CloudWatch log stream name for logging. This value is required if CloudWatch logging is enabled.

              

              

            

          

        

      RedshiftDestinationDescription -> (structure)

        

        The destination in Amazon Redshift.

        

        RoleARN -> (string)

          

          The ARN of the AWS credentials.

          

          

        ClusterJDBCURL -> (string)

          

          The database connection string.

          

          

        CopyCommand -> (structure)

          

          The ``COPY`` command.

          

          DataTableName -> (string)

            

            The name of the target table. The table must already exist in the database.

            

            

          DataTableColumns -> (string)

            

            A comma-separated list of column names.

            

            

          CopyOptions -> (string)

            

            Optional parameters to use with the Amazon Redshift ``COPY`` command. For more information, see the "Optional Parameters" section of `Amazon Redshift COPY command <http://docs.aws.amazon.com/redshift/latest/dg/r_COPY.html>`_ . Some possible examples that would apply to Firehose are as follows:

             

             ``delimiter '\t' lzop;`` - fields are delimited with "\t" (TAB character) and compressed using lzop.

             

             ``delimiter '|`` - fields are delimited with "|" (this is the default delimiter).

             

             ``delimiter '|' escape`` - the delimiter should be escaped.

             

             ``fixedwidth 'venueid:3,venuename:25,venuecity:12,venuestate:2,venueseats:6'`` - fields are fixed width in the source, with each width specified after every column in the table.

             

             ``JSON 's3://mybucket/jsonpaths.txt'`` - data is in JSON format, and the path specified is the format of the data.

             

            For more examples, see `Amazon Redshift COPY command examples <http://docs.aws.amazon.com/redshift/latest/dg/r_COPY_command_examples.html>`_ .

            

            

          

        Username -> (string)

          

          The name of the user.

          

          

        RetryOptions -> (structure)

          

          The retry behavior in the event that Firehose is unable to deliver documents to Amazon Redshift. Default value is 3600 (60 minutes).

          

          DurationInSeconds -> (integer)

            

            The length of time during which Firehose retries delivery after a failure, starting from the initial request and including the first attempt. The default value is 3600 seconds (60 minutes). Firehose does not retry if the value of ``DurationInSeconds`` is 0 (zero) or if the first delivery attempt takes longer than the current value.

            

            

          

        S3DestinationDescription -> (structure)

          

          The Amazon S3 destination.

          

          RoleARN -> (string)

            

            The ARN of the AWS credentials.

            

            

          BucketARN -> (string)

            

            The ARN of the S3 bucket.

            

            

          Prefix -> (string)

            

            The "YYYY/MM/DD/HH" time format prefix is automatically used for delivered S3 files. You can specify an extra prefix to be added in front of the time format prefix. Note that if the prefix ends with a slash, it appears as a folder in the S3 bucket. For more information, see `Amazon S3 Object Name Format <http://docs.aws.amazon.com/firehose/latest/dev/basic-deliver.html>`_ in the *Amazon Kinesis Firehose Developer Guide* .

            

            

          BufferingHints -> (structure)

            

            The buffering option. If no value is specified, **BufferingHints** object default values are used.

            

            SizeInMBs -> (integer)

              

              Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

               

              We recommend setting this parameter to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec, the value should be 10 MB or higher.

              

              

            IntervalInSeconds -> (integer)

              

              Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300.

              

              

            

          CompressionFormat -> (string)

            

            The compression format. If no value is specified, the default is ``UNCOMPRESSED`` .

            

            

          EncryptionConfiguration -> (structure)

            

            The encryption configuration. If no value is specified, the default is no encryption.

            

            NoEncryptionConfig -> (string)

              

              Specifically override existing encryption information to ensure no encryption is used.

              

              

            KMSEncryptionConfig -> (structure)

              

              The encryption key.

              

              AWSKMSKeyARN -> (string)

                

                The ARN of the encryption key. Must belong to the same region as the destination Amazon S3 bucket.

                

                

              

            

          CloudWatchLoggingOptions -> (structure)

            

            The CloudWatch logging options for your delivery stream.

            

            Enabled -> (boolean)

              

              Enables or disables CloudWatch logging.

              

              

            LogGroupName -> (string)

              

              The CloudWatch group name for logging. This value is required if CloudWatch logging is enabled.

              

              

            LogStreamName -> (string)

              

              The CloudWatch log stream name for logging. This value is required if CloudWatch logging is enabled.

              

              

            

          

        ProcessingConfiguration -> (structure)

          

          The data processing configuration.

          

          Enabled -> (boolean)

            

            Enables or disables data processing.

            

            

          Processors -> (list)

            

            The data processors.

            

            (structure)

              

              Describes a data processor.

              

              Type -> (string)

                

                The type of processor.

                

                

              Parameters -> (list)

                

                The processor parameters.

                

                (structure)

                  

                  Describes the processor parameter.

                  

                  ParameterName -> (string)

                    

                    The name of the parameter.

                    

                    

                  ParameterValue -> (string)

                    

                    The parameter value.

                    

                    

                  

                

              

            

          

        S3BackupMode -> (string)

          

          The Amazon S3 backup mode.

          

          

        S3BackupDescription -> (structure)

          

          The configuration for backup in Amazon S3.

          

          RoleARN -> (string)

            

            The ARN of the AWS credentials.

            

            

          BucketARN -> (string)

            

            The ARN of the S3 bucket.

            

            

          Prefix -> (string)

            

            The "YYYY/MM/DD/HH" time format prefix is automatically used for delivered S3 files. You can specify an extra prefix to be added in front of the time format prefix. Note that if the prefix ends with a slash, it appears as a folder in the S3 bucket. For more information, see `Amazon S3 Object Name Format <http://docs.aws.amazon.com/firehose/latest/dev/basic-deliver.html>`_ in the *Amazon Kinesis Firehose Developer Guide* .

            

            

          BufferingHints -> (structure)

            

            The buffering option. If no value is specified, **BufferingHints** object default values are used.

            

            SizeInMBs -> (integer)

              

              Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

               

              We recommend setting this parameter to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec, the value should be 10 MB or higher.

              

              

            IntervalInSeconds -> (integer)

              

              Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300.

              

              

            

          CompressionFormat -> (string)

            

            The compression format. If no value is specified, the default is ``UNCOMPRESSED`` .

            

            

          EncryptionConfiguration -> (structure)

            

            The encryption configuration. If no value is specified, the default is no encryption.

            

            NoEncryptionConfig -> (string)

              

              Specifically override existing encryption information to ensure no encryption is used.

              

              

            KMSEncryptionConfig -> (structure)

              

              The encryption key.

              

              AWSKMSKeyARN -> (string)

                

                The ARN of the encryption key. Must belong to the same region as the destination Amazon S3 bucket.

                

                

              

            

          CloudWatchLoggingOptions -> (structure)

            

            The CloudWatch logging options for your delivery stream.

            

            Enabled -> (boolean)

              

              Enables or disables CloudWatch logging.

              

              

            LogGroupName -> (string)

              

              The CloudWatch group name for logging. This value is required if CloudWatch logging is enabled.

              

              

            LogStreamName -> (string)

              

              The CloudWatch log stream name for logging. This value is required if CloudWatch logging is enabled.

              

              

            

          

        CloudWatchLoggingOptions -> (structure)

          

          The CloudWatch logging options for your delivery stream.

          

          Enabled -> (boolean)

            

            Enables or disables CloudWatch logging.

            

            

          LogGroupName -> (string)

            

            The CloudWatch group name for logging. This value is required if CloudWatch logging is enabled.

            

            

          LogStreamName -> (string)

            

            The CloudWatch log stream name for logging. This value is required if CloudWatch logging is enabled.

            

            

          

        

      ElasticsearchDestinationDescription -> (structure)

        

        The destination in Amazon ES.

        

        RoleARN -> (string)

          

          The ARN of the AWS credentials.

          

          

        DomainARN -> (string)

          

          The ARN of the Amazon ES domain.

          

          

        IndexName -> (string)

          

          The Elasticsearch index name.

          

          

        TypeName -> (string)

          

          The Elasticsearch type name.

          

          

        IndexRotationPeriod -> (string)

          

          The Elasticsearch index rotation period

          

          

        BufferingHints -> (structure)

          

          The buffering options.

          

          IntervalInSeconds -> (integer)

            

            Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300 (5 minutes).

            

            

          SizeInMBs -> (integer)

            

            Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

             

            We recommend setting this parameter to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec, the value should be 10 MB or higher.

            

            

          

        RetryOptions -> (structure)

          

          The Amazon ES retry options.

          

          DurationInSeconds -> (integer)

            

            After an initial failure to deliver to Amazon ES, the total amount of time during which Firehose re-attempts delivery (including the first attempt). After this time has elapsed, the failed documents are written to Amazon S3. Default value is 300 seconds (5 minutes). A value of 0 (zero) results in no retries.

            

            

          

        S3BackupMode -> (string)

          

          The Amazon S3 backup mode.

          

          

        S3DestinationDescription -> (structure)

          

          The Amazon S3 destination.

          

          RoleARN -> (string)

            

            The ARN of the AWS credentials.

            

            

          BucketARN -> (string)

            

            The ARN of the S3 bucket.

            

            

          Prefix -> (string)

            

            The "YYYY/MM/DD/HH" time format prefix is automatically used for delivered S3 files. You can specify an extra prefix to be added in front of the time format prefix. Note that if the prefix ends with a slash, it appears as a folder in the S3 bucket. For more information, see `Amazon S3 Object Name Format <http://docs.aws.amazon.com/firehose/latest/dev/basic-deliver.html>`_ in the *Amazon Kinesis Firehose Developer Guide* .

            

            

          BufferingHints -> (structure)

            

            The buffering option. If no value is specified, **BufferingHints** object default values are used.

            

            SizeInMBs -> (integer)

              

              Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

               

              We recommend setting this parameter to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec, the value should be 10 MB or higher.

              

              

            IntervalInSeconds -> (integer)

              

              Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300.

              

              

            

          CompressionFormat -> (string)

            

            The compression format. If no value is specified, the default is ``UNCOMPRESSED`` .

            

            

          EncryptionConfiguration -> (structure)

            

            The encryption configuration. If no value is specified, the default is no encryption.

            

            NoEncryptionConfig -> (string)

              

              Specifically override existing encryption information to ensure no encryption is used.

              

              

            KMSEncryptionConfig -> (structure)

              

              The encryption key.

              

              AWSKMSKeyARN -> (string)

                

                The ARN of the encryption key. Must belong to the same region as the destination Amazon S3 bucket.

                

                

              

            

          CloudWatchLoggingOptions -> (structure)

            

            The CloudWatch logging options for your delivery stream.

            

            Enabled -> (boolean)

              

              Enables or disables CloudWatch logging.

              

              

            LogGroupName -> (string)

              

              The CloudWatch group name for logging. This value is required if CloudWatch logging is enabled.

              

              

            LogStreamName -> (string)

              

              The CloudWatch log stream name for logging. This value is required if CloudWatch logging is enabled.

              

              

            

          

        ProcessingConfiguration -> (structure)

          

          The data processing configuration.

          

          Enabled -> (boolean)

            

            Enables or disables data processing.

            

            

          Processors -> (list)

            

            The data processors.

            

            (structure)

              

              Describes a data processor.

              

              Type -> (string)

                

                The type of processor.

                

                

              Parameters -> (list)

                

                The processor parameters.

                

                (structure)

                  

                  Describes the processor parameter.

                  

                  ParameterName -> (string)

                    

                    The name of the parameter.

                    

                    

                  ParameterValue -> (string)

                    

                    The parameter value.

                    

                    

                  

                

              

            

          

        CloudWatchLoggingOptions -> (structure)

          

          The CloudWatch logging options.

          

          Enabled -> (boolean)

            

            Enables or disables CloudWatch logging.

            

            

          LogGroupName -> (string)

            

            The CloudWatch group name for logging. This value is required if CloudWatch logging is enabled.

            

            

          LogStreamName -> (string)

            

            The CloudWatch log stream name for logging. This value is required if CloudWatch logging is enabled.

            

            

          

        

      

    

  HasMoreDestinations -> (boolean)

    

    Indicates whether there are more destinations available to list.

    

    

  

