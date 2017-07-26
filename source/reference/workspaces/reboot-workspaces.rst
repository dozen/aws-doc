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

   

  This operation is asynchronous and returns before the WorkSpaces have rebooted.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workspaces-2015-04-08/RebootWorkspaces>`_


========
Synopsis
========

::

    reboot-workspaces
  --reboot-workspace-requests <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FailedRequests -> (list)

  

  An array of structures representing any WorkSpaces that could not be rebooted.

  

  (structure)

    

    Contains information about a WorkSpace that could not be rebooted ( reboot-workspaces ), rebuilt ( rebuild-workspaces ), terminated ( terminate-workspaces ), started ( start-workspaces ), or stopped ( stop-workspaces ).

    

    WorkspaceId -> (string)

      

      The identifier of the WorkSpace.

      

      

    ErrorCode -> (string)

      

      The error code.

      

      

    ErrorMessage -> (string)

      

      The textual error message.

      

      

    

  

