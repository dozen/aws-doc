[ :ref:`aws <cli:aws>` . :ref:`workspaces <cli:aws workspaces>` ]

.. _cli:aws workspaces modify-workspace-properties:


***************************
modify-workspace-properties
***************************



===========
Description
===========



Modifies the WorkSpace properties, including the running mode and AutoStop time.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workspaces-2015-04-08/ModifyWorkspaceProperties>`_


========
Synopsis
========

::

    modify-workspace-properties
  --workspace-id <value>
  --workspace-properties <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--workspace-id`` (string)


  The ID of the WorkSpace.

  

``--workspace-properties`` (structure)


  The WorkSpace properties of the request.

  



Shorthand Syntax::

    RunningMode=string,RunningModeAutoStopTimeoutInMinutes=integer




JSON Syntax::

  {
    "RunningMode": "AUTO_STOP"|"ALWAYS_ON",
    "RunningModeAutoStopTimeoutInMinutes": integer
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

