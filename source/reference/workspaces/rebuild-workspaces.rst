[ :ref:`aws <cli:aws>` . :ref:`workspaces <cli:aws workspaces>` ]

.. _cli:aws workspaces rebuild-workspaces:


******************
rebuild-workspaces
******************



===========
Description
===========



Rebuilds the specified WorkSpaces.

 

Rebuilding a WorkSpace is a potentially destructive action that can result in the loss of data. Rebuilding a WorkSpace causes the following to occur:

 

 
* The system is restored to the image of the bundle that the WorkSpace is created from. Any applications that have been installed, or system settings that have been made since the WorkSpace was created will be lost. 
 
* The data drive (D drive) is re-created from the last automatic snapshot taken of the data drive. The current contents of the data drive are overwritten. Automatic snapshots of the data drive are taken every 12 hours, so the snapshot can be as much as 12 hours old. 
 

 

To be able to rebuild a WorkSpace, the WorkSpace must have a **State** of ``AVAILABLE`` or ``ERROR`` .

 

.. note::

   

  This operation is asynchronous and returns before the WorkSpaces have been completely rebuilt.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workspaces-2015-04-08/RebuildWorkspaces>`_


========
Synopsis
========

::

    rebuild-workspaces
  --rebuild-workspace-requests <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rebuild-workspace-requests`` (list)


  An array of structures that specify the WorkSpaces to rebuild.

  



Shorthand Syntax::

    --rebuild-workspace-requests WorkspaceId1 WorkspaceId2 WorkspaceId3




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

  

  An array of structures representing any WorkSpaces that could not be rebuilt.

  

  (structure)

    

    Contains information about a WorkSpace that could not be rebooted ( reboot-workspaces ), rebuilt ( rebuild-workspaces ), terminated ( terminate-workspaces ), started ( start-workspaces ), or stopped ( stop-workspaces ).

    

    WorkspaceId -> (string)

      

      The identifier of the WorkSpace.

      

      

    ErrorCode -> (string)

      

      The error code.

      

      

    ErrorMessage -> (string)

      

      The textual error message.

      

      

    

  

