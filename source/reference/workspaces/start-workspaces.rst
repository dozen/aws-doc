[ :ref:`aws <cli:aws>` . :ref:`workspaces <cli:aws workspaces>` ]

.. _cli:aws workspaces start-workspaces:


****************
start-workspaces
****************



===========
Description
===========



Starts the specified WorkSpaces. The WorkSpaces must have a running mode of AutoStop and a state of STOPPED.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workspaces-2015-04-08/StartWorkspaces>`_


========
Synopsis
========

::

    start-workspaces
  --start-workspace-requests <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--start-workspace-requests`` (list)


  The requests.

  



Shorthand Syntax::

    WorkspaceId=string ...




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

  

  The failed requests.

  

  (structure)

    

    Contains information about a WorkSpace that could not be rebooted ( reboot-workspaces ), rebuilt ( rebuild-workspaces ), terminated ( terminate-workspaces ), started ( start-workspaces ), or stopped ( stop-workspaces ).

    

    WorkspaceId -> (string)

      

      The identifier of the WorkSpace.

      

      

    ErrorCode -> (string)

      

      The error code.

      

      

    ErrorMessage -> (string)

      

      The textual error message.

      

      

    

  

