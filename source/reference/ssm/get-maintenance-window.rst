[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm get-maintenance-window:


**********************
get-maintenance-window
**********************



===========
Description
===========



Retrieves a Maintenance Window.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/GetMaintenanceWindow>`_


========
Synopsis
========

::

    get-maintenance-window
  --window-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--window-id`` (string)


  The ID of the desired Maintenance Window.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get information about a maintenance window**

This example gets details about a maintenance window.

Command::

  aws ssm get-maintenance-window --window-id "mw-03eb9db42890fb82d"

Output::

  {
    "Cutoff": 1,
    "Name": "TestMaintWin",
    "Schedule": "cron(0 */30 * * * ? *)",
    "Enabled": true,
    "AllowUnassociatedTargets": false,
    "WindowId": "mw-03eb9db42890fb82d",
    "ModifiedDate": 1487614445.527,
    "CreatedDate": 1487614445.527,
    "Duration": 2
  }


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

  

  Whether the Maintenance Windows is enabled.

  

  

CreatedDate -> (timestamp)

  

  The date the Maintenance Window was created.

  

  

ModifiedDate -> (timestamp)

  

  The date the Maintenance Window was last modified.

  

  

