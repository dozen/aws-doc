[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm list-commands:


*************
list-commands
*************



===========
Description
===========



Lists the commands requested by users of the AWS account.



``list-commands`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Commands``


========
Synopsis
========

::

    list-commands
  [--command-id <value>]
  [--instance-id <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--command-id`` (string)
(Optional) If provided, lists only the specified command.

``--instance-id`` (string)
(Optional) Lists commands issued against this instance ID.

``--filters`` (list)
(Optional) One or more filters. Use a filter to return a more specific list of results.



Shorthand Syntax::

    key=string,value=string ...




JSON Syntax::

  [
    {
      "key": "InvokedAfter"|"InvokedBefore"|"Status",
      "value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``next-token`` will be provided in the output that you can use to resume pagination. This ``next-token`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Commands -> (list)

  (Optional) The list of commands requested by the user.

  (structure)

    Describes a command request.

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

      

    

  

NextToken -> (string)

  (Optional) The token for the next set of items to return. (You received this token from a previous call.)

  

