[ :ref:`aws <cli:aws>` . :ref:`pinpoint <cli:aws pinpoint>` ]

.. _cli:aws pinpoint create-import-job:


*****************
create-import-job
*****************



===========
Description
===========

Creates or updates an import job.

========
Synopsis
========

::

    create-import-job
  --application-id <value>
  --import-job-request <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-id`` (string)


``--import-job-request`` (structure)




Shorthand Syntax::

    DefineSegment=boolean,ExternalId=string,Format=string,RegisterEndpoints=boolean,RoleArn=string,S3Url=string,SegmentId=string,SegmentName=string




JSON Syntax::

  {
    "DefineSegment": true|false,
    "ExternalId": "string",
    "Format": "CSV"|"JSON",
    "RegisterEndpoints": true|false,
    "RoleArn": "string",
    "S3Url": "string",
    "SegmentId": "string",
    "SegmentName": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ImportJobResponse -> (structure)

  

  ApplicationId -> (string)

    The unique ID of the application to which the import job applies.

    

  CompletedPieces -> (integer)

    The number of pieces that have successfully imported as of the time of the request.

    

  CompletionDate -> (string)

    The date the import job completed in ISO 8601 format.

    

  CreationDate -> (string)

    The date the import job was created in ISO 8601 format.

    

  Definition -> (structure)

    The import job settings.

    DefineSegment -> (boolean)

      Sets whether the endpoints create a segment when they are imported.

      

    ExternalId -> (string)

      A unique, custom ID assigned to the IAM role that restricts who can assume the role. 

      

    Format -> (string)

      The format of the files that contain the endpoint definitions. Valid values: CSV, JSON

      

    RegisterEndpoints -> (boolean)

      Sets whether the endpoints are registered with Amazon Pinpoint when they are imported.

      

    RoleArn -> (string)

      The Amazon Resource Name (ARN) of an IAM role that grants Amazon Pinpoint access to the Amazon S3 location that contains the endpoints to import.

      

    S3Url -> (string)

      A URL that points to the location within an Amazon S3 bucket that contains the endpoints to import. The location can be a folder or a single file. The URL should follow this format: s3://bucket-name/folder-name/file-name Amazon Pinpoint will import endpoints from this location and any subfolders it contains.

      

    SegmentId -> (string)

      The ID of the segment to update if the import job is meant to update an existing segment.

      

    SegmentName -> (string)

      A custom name for the segment created by the import job. Use if DefineSegment is true.

      

    

  FailedPieces -> (integer)

    The number of pieces that have failed to import as of the time of the request.

    

  Failures -> (list)

    Provides up to 100 of the first failed entries for the job, if any exist.

    (string)

      

      

    

  Id -> (string)

    The unique ID of the import job.

    

  JobStatus -> (string)

    The status of the import job. Valid values: CREATED, INITIALIZING, PROCESSING, COMPLETING, COMPLETED, FAILING, FAILED The job status is FAILED if one or more pieces failed to import.

    

  TotalFailures -> (integer)

    The number of endpoints that failed to import; for example, because of syntax errors.

    

  TotalPieces -> (integer)

    The total number of pieces that must be imported to finish the job. Each piece is an approximately equal portion of the endpoints to import.

    

  TotalProcessed -> (integer)

    The number of endpoints that were processed by the import job.

    

  Type -> (string)

    The job type. Will be Import.

    

  

