[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling delete-scheduled-action:


***********************
delete-scheduled-action
***********************



===========
Description
===========



Deletes the specified scheduled action.



========
Synopsis
========

::

    delete-scheduled-action
  [--auto-scaling-group-name <value>]
  --scheduled-action-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the Auto Scaling group.

  

``--scheduled-action-name`` (string)


  The name of the action to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a scheduled action from an Auto Scaling group**

This example deletes the specified scheduled action from the specified Auto Scaling group::

	aws autoscaling delete-scheduled-action --auto-scaling-group-name my-auto-scaling-group --scheduled-action-name my-scheduled-action


======
Output
======

None