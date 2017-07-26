[ :ref:`aws <cli:aws>` . :ref:`firehose <cli:aws firehose>` ]

.. _cli:aws firehose describe-delivery-stream:


************************
describe-delivery-stream
************************



===========
Description
===========



Describes the specified delivery stream and gets the status. For example, after your delivery stream is created, call  describe-delivery-stream to see if the delivery stream is ``ACTIVE`` and therefore ready for data to be sent to it.



========
Synopsis
========

::

    describe-delivery-stream
  --delivery-stream-name <value>
  [--limit <value>]
  [--exclusive-start-destination-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--delivery-stream-name`` (string)


  The name of the delivery stream.

  

``--limit`` (integer)


  The limit on the number of destinations to return. Currently, you can have one destination per delivery stream.

  

``--exclusive-start-destination-id`` (string)


  Specifies the destination ID to start returning the destination information. Currently Amazon Kinesis Firehose supports one destination per delivery stream.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

    

    Used when calling the  update-destination operation. Each time the destination is updated for the delivery stream, the VersionId is changed, and the current VersionId is required when updating the destination. This is so that the service knows it is applying the changes to the correct version of the delivery stream.

    

    

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

        

        The Amazon S3 destination.

        

        RoleARN -> (string)

          

          The ARN of the AWS credentials.

          

          

        BucketARN -> (string)

          

          The ARN of the S3 bucket.

          

          

        Prefix -> (string)

          

          The "YYYY/MM/DD/HH" time format prefix is automatically used for delivered S3 files. You can specify an extra prefix to be added in front of the time format prefix. Note that if the prefix ends with a slash, it appears as a folder in the S3 bucket. For more information, see `Amazon S3 Object Name Format`_ in the `guide-fh-dev`_ .

          

          

        BufferingHints -> (structure)

          

          The buffering option. If no value is specified, ``BufferingHints`` object default values are used.

          

          SizeInMBs -> (integer)

            

            Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

             

            We recommend setting SizeInMBs to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec set SizeInMBs to be 10 MB or higher.

            

            

          IntervalInSeconds -> (integer)

            

            Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300.

            

            

          

        CompressionFormat -> (string)

          

          The compression format. If no value is specified, the default is ``NOCOMPRESSION`` .

          

          

        EncryptionConfiguration -> (structure)

          

          The encryption configuration. If no value is specified, the default is no encryption.

          

          NoEncryptionConfig -> (string)

            

            Specifically override existing encryption information to ensure no encryption is used.

            

            

          KMSEncryptionConfig -> (structure)

            

            The encryption key.

            

            AWSKMSKeyARN -> (string)

              

              The ARN of the encryption key. Must belong to the same region as the destination Amazon S3 bucket.

              

              

            

          

        

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

            

            Optional parameters to use with the Amazon Redshift ``COPY`` command. For more information, see the "Optional Parameters" section of `Amazon Redshift COPY command`_ . Some possible examples that would apply to Amazon Kinesis Firehose are as follows.

             

            ``delimiter '\t' lzop;`` - fields are delimited with "\t" (TAB character) and compressed using lzop.

             

            ``delimiter '|`` - fields are delimited with "|" (this is the default delimiter).

             

            ``delimiter '|' escape`` - the delimiter should be escaped.

             

            ``fixedwidth 'venueid:3,venuename:25,venuecity:12,venuestate:2,venueseats:6'`` - fields are fixed width in the source, with each width specified after every column in the table.

             

             ``JSON 's3://mybucket/jsonpaths.txt'`` - data is in JSON format, and the path specified is the format of the data.

             

            For more examples, see and `Amazon Redshift COPY command exmaples`_ .

            

            

          

        Username -> (string)

          

          The name of the user.

          

          

        S3DestinationDescription -> (structure)

          

          The Amazon S3 destination.

          

          RoleARN -> (string)

            

            The ARN of the AWS credentials.

            

            

          BucketARN -> (string)

            

            The ARN of the S3 bucket.

            

            

          Prefix -> (string)

            

            The "YYYY/MM/DD/HH" time format prefix is automatically used for delivered S3 files. You can specify an extra prefix to be added in front of the time format prefix. Note that if the prefix ends with a slash, it appears as a folder in the S3 bucket. For more information, see `Amazon S3 Object Name Format`_ in the `guide-fh-dev`_ .

            

            

          BufferingHints -> (structure)

            

            The buffering option. If no value is specified, ``BufferingHints`` object default values are used.

            

            SizeInMBs -> (integer)

              

              Buffer incoming data to the specified size, in MBs, before delivering it to the destination. The default value is 5.

               

              We recommend setting SizeInMBs to a value greater than the amount of data you typically ingest into the delivery stream in 10 seconds. For example, if you typically ingest data at 1 MB/sec set SizeInMBs to be 10 MB or higher.

              

              

            IntervalInSeconds -> (integer)

              

              Buffer incoming data for the specified period of time, in seconds, before delivering it to the destination. The default value is 300.

              

              

            

          CompressionFormat -> (string)

            

            The compression format. If no value is specified, the default is ``NOCOMPRESSION`` .

            

            

          EncryptionConfiguration -> (structure)

            

            The encryption configuration. If no value is specified, the default is no encryption.

            

            NoEncryptionConfig -> (string)

              

              Specifically override existing encryption information to ensure no encryption is used.

              

              

            KMSEncryptionConfig -> (structure)

              

              The encryption key.

              

              AWSKMSKeyARN -> (string)

                

                The ARN of the encryption key. Must belong to the same region as the destination Amazon S3 bucket.

                

                

              

            

          

        

      

    

  HasMoreDestinations -> (boolean)

    

    Indicates whether there are more destinations available to list.

    

    

  



.. _Amazon S3 Object Name Format: http://docs.aws.amazon.com/firehose/latest/dev/basic-deliver.html
.. _Amazon Redshift COPY command exmaples: http://docs.aws.amazon.com/redshift/latest/dg/r_COPY_command_examples.html
.. _guide-fh-dev: http://docs.aws.amazon.com/firehose/latest/dev/
.. _Amazon Redshift COPY command: http://docs.aws.amazon.com/redshift/latest/dg/r_COPY.html
