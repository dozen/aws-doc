[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm send-command:


************
send-command
************



===========
Description
===========

Executes commands on one or more remote instances.

========
Synopsis
========

::

    send-command
  --instance-ids <value>
  --document-name <value>
  [--timeout-seconds <value>]
  [--comment <value>]
  [--parameters <value>]
  [--output-s3-bucket-name <value>]
  [--output-s3-key-prefix <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-ids`` (list)
Required. The instance IDs where the command should execute.



Syntax::

  "string" "string" ...



``--document-name`` (string)
Required. The name of the SSM document to execute. This can be an SSM public document or a custom document.

``--timeout-seconds`` (integer)
If this time is reached and the command has not already started executing, it will not execute.

``--comment`` (string)
User-specified information about the command, such as a brief description of what the command should do.

``--parameters`` (map)
The required and optional parameters specified in the SSM document being executed.



Shorthand Syntax::

    KeyName1=string,string,KeyName2=string,string




JSON Syntax::

  {"string": ["string", ...]
    ...}



``--output-s3-bucket-name`` (string)
The name of the S3 bucket where command execution responses should be stored.

``--output-s3-key-prefix`` (string)
The directory structure within the S3 bucket where the responses should be stored.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Command -> (structure)

  The request as it was received by SSM. Also provides the command ID which can be used future references to this request.

  CommandId -> (string)

    A unique identifier for this command.

    

  DocumentName -> (string)

    The name of the SSM document requested for execution.

    

  Comment -> (string)

    User-specified information about the command, such as a brief description of what the command should do.

    

  ExpiresAfter -> (timestamp)

    If this time is reached and the command has not already started executing, it will not execute. Calculated based on the ExpiresAfter user input provided as part of the send-command API.

    

  Parameters -> (map)

    The parameter values to be inserted in the SSM document when executing the command.

    key -> (string)

      

      

    value -> (list)

      

      (string)

        

        

      

    

  InstanceIds -> (list)

    The instance IDs against which this command was requested.

    (string)

      

      

    

  RequestedDateTime -> (timestamp)

    The date and time the command was requested.

    

  Status -> (string)

    The status of the command.

    

  OutputS3BucketName -> (string)

    The S3 bucket where the responses to the command executions should be stored. This was requested when issuing the command.

    

  OutputS3KeyPrefix -> (string)

    The S3 directory path inside the bucket where the responses to the command executions should be stored. This was requested when issuing the command.

    

  

