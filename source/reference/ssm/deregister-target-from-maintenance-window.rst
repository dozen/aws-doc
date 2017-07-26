[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm deregister-target-from-maintenance-window:


*****************************************
deregister-target-from-maintenance-window
*****************************************



===========
Description
===========



Removes a target from a Maintenance Window.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DeregisterTargetFromMaintenanceWindow>`_


========
Synopsis
========

::

    deregister-target-from-maintenance-window
  --window-id <value>
  --window-target-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--window-id`` (string)


  The ID of the Maintenance Window the target should be removed from.

  

``--window-target-id`` (string)


  The ID of the target definition to remove.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To remove a target from a maintenance window**

This example removes a target from a maintenance window.

Command::

  aws ssm deregister-target-from-maintenance-window --window-id "mw-ab12cd34ef56gh78" --window-target-id "1a2b3c4d-1a2b-1a2b-1a2b-1a2b3c4d-1a2"

Output::

  {
    "WindowId":"mw-ab12cd34ef56gh78",
    "WindowTargetId":"1a2b3c4d-1a2b-1a2b-1a2b-1a2b3c4d-1a2"
  }


======
Output
======

WindowId -> (string)

  

  The ID of the Maintenance Window the target was removed from.

  

  

WindowTargetId -> (string)

  

  The ID of the removed target definition.

  

  

