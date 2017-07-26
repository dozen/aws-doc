[ :ref:`aws <cli:aws>` . :ref:`workspaces <cli:aws workspaces>` ]

.. _cli:aws workspaces terminate-workspaces:


********************
terminate-workspaces
********************



===========
Description
===========



Terminates the specified WorkSpaces.

 

Terminating a WorkSpace is a permanent action and cannot be undone. The user's data is not maintained and will be destroyed. If you need to archive any user data, contact Amazon Web Services before terminating the WorkSpace.

 

You can terminate a WorkSpace that is in any state except ``SUSPENDED`` .

 

.. note::

   

  This operation is asynchronous and returns before the WorkSpaces have been completely terminated.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workspaces-2015-04-08/TerminateWorkspaces>`_


========
Synopsis
========

::

    terminate-workspaces
  --terminate-workspace-requests <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--terminate-workspace-requests`` (list)


  An array of structures that specify the WorkSpaces to terminate.

  



Shorthand Syntax::

    --terminate-workspace-requests WorkspaceId1 WorkspaceId2 WorkspaceId3




JSON Syntax::

  [
    {
      "WorkspaceId": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To terminate a WorkSpace**

This example terminates the specified WorkSpace.

Command::

  aws workspaces terminate-workspaces --terminate-workspace-requests wsb-3t36q0xfc

Output::

  {
    "FailedRequests": []
  }

======
Output
======

FailedRequests -> (list)

  

  An array of structures representing any WorkSpaces that could not be terminated.

  

  (structure)

    

    Contains information about a WorkSpace that could not be rebooted ( reboot-workspaces ), rebuilt ( rebuild-workspaces ), terminated ( terminate-workspaces ), started ( start-workspaces ), or stopped ( stop-workspaces ).

    

    WorkspaceId -> (string)

      

      The identifier of the WorkSpace.

      

      

    ErrorCode -> (string)

      

      The error code.

      

      

    ErrorMessage -> (string)

      

      The textual error message.

      

      

    

  

