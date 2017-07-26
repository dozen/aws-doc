[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling delete-scheduled-action:


***********************
delete-scheduled-action
***********************



===========
Description
===========



Deletes the specified scheduled action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DeleteScheduledAction>`_


========
Synopsis
========

::

    delete-scheduled-action
  --auto-scaling-group-name <value>
  --scheduled-action-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the Auto Scaling group.

  

``--scheduled-action-name`` (string)


  The name of the action to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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