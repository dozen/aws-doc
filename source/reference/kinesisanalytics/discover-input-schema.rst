[ :ref:`aws <cli:aws>` . :ref:`kinesisanalytics <cli:aws kinesisanalytics>` ]

.. _cli:aws kinesisanalytics discover-input-schema:


*********************
discover-input-schema
*********************



===========
Description
===========



Infers a schema by evaluating sample records on the specified streaming source (Amazon Kinesis stream or Amazon Kinesis Firehose delivery stream). In the response, the operation returns the inferred schema and also the sample records that the operation used to infer the schema.

 

You can use the inferred schema when configuring a streaming source for your application. For conceptual information, see `Configuring Application Input <http://docs.aws.amazon.com/kinesisanalytics/latest/dev/how-it-works-input.html>`_ . Note that when you create an application using the Amazon Kinesis Analytics console, the console uses this operation to infer a schema and show it in the console user interface. 

 

This operation requires permissions to perform the ``kinesisanalytics:DiscoverInputSchema`` action. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesisanalytics-2015-08-14/DiscoverInputSchema>`_


========
Synopsis
========

::

    discover-input-schema
  --resource-arn <value>
  --role-arn <value>
  --input-starting-position-configuration <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn`` (string)


  Amazon Resource Name (ARN) of the streaming source.

  

``--role-arn`` (string)


  ARN of the IAM role that Amazon Kinesis Analytics can assume to access the stream on your behalf.

  

``--input-starting-position-configuration`` (structure)


  Point at which you want Amazon Kinesis Analytics to start reading records from the specified streaming source discovery purposes.

  



Shorthand Syntax::

    InputStartingPosition=string




JSON Syntax::

  {
    "InputStartingPosition": "NOW"|"TRIM_HORIZON"|"LAST_STOPPED_POINT"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

InputSchema -> (structure)

  

  Schema inferred from the streaming source. It identifies the format of the data in the streaming source and how each data element maps to corresponding columns in the in-application stream that you can create.

  

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

        

        

      

    

  

ParsedInputRecords -> (list)

  

  An array of elements, where each element corresponds to a row in a stream record (a stream record can have more than one row).

  

  (list)

    

    (string)

      

      

    

  

RawInputRecords -> (list)

  

  Raw stream data that was sampled to infer the schema.

  

  (string)

    

    

  

