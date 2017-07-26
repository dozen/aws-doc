[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm delete-maintenance-window:


*************************
delete-maintenance-window
*************************



===========
Description
===========



Deletes a Maintenance Window.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DeleteMaintenanceWindow>`_


========
Synopsis
========

::

    delete-maintenance-window
  --window-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--window-id`` (string)


  The ID of the Maintenance Window to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a maintenance window**

This example removes a maintenance window.

Command::

  aws ssm delete-maintenance-window --window-id "mw-1a2b3c4d5e6f7g8h9"

Output::

  {
	"WindowId":"mw-1a2b3c4d5e6f7g8h9"
  }


======
Output
======

WindowId -> (string)

  

  The ID of the deleted Maintenance Window.

  

  

