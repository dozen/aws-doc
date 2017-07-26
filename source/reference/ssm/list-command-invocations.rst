[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm list-command-invocations:


************************
list-command-invocations
************************



===========
Description
===========

An invocation is copy of a command sent to a specific instance. A command can apply to one or more instances. A command invocation applies to one instance. For example, if a user executes send-command against three instances, then a command invocation is created for each requested instance ID. list-command-invocations provide status about command execution.

``list-command-invocations`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``CommandInvocations``


========
Synopsis
========

::

    list-command-invocations
  [--command-id <value>]
  [--instance-id <value>]
  [--filters <value>]
  [--details | --no-details]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--command-id`` (string)
(Optional) The invocations for a specific command ID.

``--instance-id`` (string)
(Optional) The command execution details for a specific instance ID.

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



``--details`` | ``--no-details`` (boolean)
(Optional) If set this returns the response of the command executions and any command output. By default this is set to False.

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

CommandInvocations -> (list)

  (Optional) A list of all invocations.

  (structure)

    An invocation is copy of a command sent to a specific instance. A command can apply to one or more instances. A command invocation applies to one instance. For example, if a user executes send-command against three instances, then a command invocation is created for each requested instance ID. A command invocation returns status and detail information about a command you executed.

    CommandId -> (string)

      The command against which this invocation was requested.

      

    InstanceId -> (string)

      The instance ID in which this invocation was requested.

      

    Comment -> (string)

      User-specified information about the command, such as a brief description of what the command should do.

      

    DocumentName -> (string)

      The document name that was requested for execution.

      

    RequestedDateTime -> (timestamp)

      The time and date the request was sent to this instance.

      

    Status -> (string)

      Whether or not the invocation succeeded, failed, or is pending.

      

    TraceOutput -> (string)

      Gets the trace output sent by the agent.

      

    CommandPlugins -> (list)

      

      (structure)

        Describes plugin details.

        Name -> (string)

          The name of the plugin. Must be one of the following: aws:updateAgent, aws:domainjoin, aws:applications, aws:runPowerShellScript, aws:psmodule, aws:cloudWatch, aws:runShellScript, or aws:updateSSMAgent.

          

        Status -> (string)

          The status of this plugin. You can execute a document with multiple plugins.

          

        ResponseCode -> (integer)

          A numeric response code generated after executing the plugin.

          

        ResponseStartDateTime -> (timestamp)

          The time the plugin started executing.

          

        ResponseFinishDateTime -> (timestamp)

          The time the plugin stopped executing. Could stop prematurely if, for example, a cancel command was sent.

          

        Output -> (string)

          Output of the plugin execution.

          

        OutputS3BucketName -> (string)

          The S3 bucket where the responses to the command executions should be stored. This was requested when issuing the command.

          

        OutputS3KeyPrefix -> (string)

          The S3 directory path inside the bucket where the responses to the command executions should be stored. This was requested when issuing the command.

          

        

      

    

  

NextToken -> (string)

  (Optional) The token for the next set of items to return. (You received this token from a previous call.)

  

