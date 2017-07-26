[ :ref:`aws <cli:aws>` . :ref:`workspaces <cli:aws workspaces>` ]

.. _cli:aws workspaces reboot-workspaces:


*****************
reboot-workspaces
*****************



===========
Description
===========



Reboots the specified WorkSpaces.

 

To be able to reboot a WorkSpace, the WorkSpace must have a **State** of ``AVAILABLE`` , ``IMPAIRED`` , or ``INOPERABLE`` .

 

.. note::

   

  This operation is asynchronous and will return before the WorkSpaces have rebooted.

   



========
Synopsis
========

::

    reboot-workspaces
  --reboot-workspace-requests <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--reboot-workspace-requests`` (list)


  An array of structures that specify the WorkSpaces to reboot.

  



Shorthand Syntax::

    --reboot-workspace-requests WorkspaceId1 WorkspaceId2 WorkspaceId3




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



======
Output
======

FailedRequests -> (list)

  

  An array of structures that represent any WorkSpaces that could not be rebooted.

  

  (structure)

    

    Contains information about a WorkSpace that could not be rebooted ( reboot-workspaces ), rebuilt ( rebuild-workspaces ), or terminated ( terminate-workspaces ).

    

    WorkspaceId -> (string)

      

      The identifier of the WorkSpace.

      

      

    ErrorCode -> (string)

      

      The error code.

      

      

    ErrorMessage -> (string)

      

      The textual error message.

      

      

    

  

