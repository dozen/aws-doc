[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm create-maintenance-window:


*************************
create-maintenance-window
*************************



===========
Description
===========



Creates a new Maintenance Window.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/CreateMaintenanceWindow>`_


========
Synopsis
========

::

    create-maintenance-window
  --name <value>
  --schedule <value>
  --duration <value>
  --cutoff <value>
  --allow-unassociated-targets | --no-allow-unassociated-targets
  [--client-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

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

  

``--client-token`` (string)


  User-provided idempotency token.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a maintenance window**

This example creates a new maintenance window with the specified name that runs at 4 PM on every Tuesday for 4 hours, with a 1 hour cutoff, and that allows unassociated targets.

Command::

  aws ssm create-maintenance-window --name "My-First-Maintenance-Window" --schedule "cron(0 16 ? * TUE *)" --duration 4 --cutoff 1 --allow-unassociated-targets

Output::

  {
	"WindowId": "mw-ab12cd34ef56gh78"
  }


======
Output
======

WindowId -> (string)

  

  The ID of the created Maintenance Window.

  

  

