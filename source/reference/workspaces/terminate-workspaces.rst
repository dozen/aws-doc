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

   

  This operation is asynchronous and will return before the WorkSpaces have been completely terminated.

   



========
Synopsis
========

::

    terminate-workspaces
  --terminate-workspace-requests <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  An array of structures that represent any WorkSpaces that could not be terminated.

  

  (structure)

    

    Contains information about a WorkSpace that could not be rebooted ( reboot-workspaces ), rebuilt ( rebuild-workspaces ), or terminated ( terminate-workspaces ).

    

    WorkspaceId -> (string)

      

      The identifier of the WorkSpace.

      

      

    ErrorCode -> (string)

      

      The error code.

      

      

    ErrorMessage -> (string)

      

      The textual error message.

      

      

    

  

