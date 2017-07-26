[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm update-maintenance-window:


*************************
update-maintenance-window
*************************



===========
Description
===========



Updates an existing Maintenance Window. Only specified parameters are modified.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/UpdateMaintenanceWindow>`_


========
Synopsis
========

::

    update-maintenance-window
  --window-id <value>
  [--name <value>]
  [--schedule <value>]
  [--duration <value>]
  [--cutoff <value>]
  [--allow-unassociated-targets | --no-allow-unassociated-targets]
  [--enabled | --no-enabled]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--window-id`` (string)


  The ID of the Maintenance Window to update.

  

``--name`` (string)


  The name of the Maintenance Window.

  

``--schedule`` (string)


  The schedule of the Maintenance Window in the form of a cron or rate expression.

  

``--duration`` (integer)


  The duration of the Maintenance Window in hours.

  

``--cutoff`` (integer)


  The number of hours before the end of the Maintenance Window that Systems Manager stops scheduling new tasks for execution.

  

``--allow-unassociated-targets`` | ``--no-allow-unassociated-targets`` (boolean)


  Whether targets must be registered with the Maintenance Window before tasks can be defined for those targets.

  

``--enabled`` | ``--no-enabled`` (boolean)


  Whether the Maintenance Window is enabled.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To update a maintenance window**

This example updates the name of a maintenance window.

Command::

  aws ssm update-maintenance-window --window-id "mw-1a2b3c4d5e6f7g8h9" --name "My-Renamed-MW"

Output::

  {
	"Cutoff": 1,
	"Name": "My-Renamed-MW",
	"Schedule": "cron(0 16 ? * TUE *)",
	"Enabled": true,
	"AllowUnassociatedTargets": true,
	"WindowId": "mw-1a2b3c4d5e6f7g8h9",
	"Duration": 4
  }

**To enable a maintenance window**

This example enables a maintenance window.

Command::

  aws ssm update-maintenance-window --window-id "mw-1a2b3c4d5e6f7g8h9" --enabled
  
**To disable a maintenance window**
  
This example disables a maintenance window.

Command::

  aws ssm update-maintenance-window --window-id "mw-1a2b3c4d5e6f7g8h9" --no-enabled
  

======
Output
======

WindowId -> (string)

  

  The ID of the created Maintenance Window.

  

  

Name -> (string)

  

  The name of the Maintenance Window.

  

  

Schedule -> (string)

  

  The schedule of the Maintenance Window in the form of a cron or rate expression.

  

  

Duration -> (integer)

  

  The duration of the Maintenance Window in hours.

  

  

Cutoff -> (integer)

  

  The number of hours before the end of the Maintenance Window that Systems Manager stops scheduling new tasks for execution.

  

  

AllowUnassociatedTargets -> (boolean)

  

  Whether targets must be registered with the Maintenance Window before tasks can be defined for those targets.

  

  

Enabled -> (boolean)

  

  Whether the Maintenance Window is enabled.

  

  

