[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling delete-lifecycle-hook:


*********************
delete-lifecycle-hook
*********************



===========
Description
===========



Deletes the specified lifecycle hook.

 

If there are any outstanding lifecycle actions, they are completed first (``ABANDON`` for launching instances, ``CONTINUE`` for terminating instances).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DeleteLifecycleHook>`_


========
Synopsis
========

::

    delete-lifecycle-hook
  --lifecycle-hook-name <value>
  --auto-scaling-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--lifecycle-hook-name`` (string)


  The name of the lifecycle hook.

  

``--auto-scaling-group-name`` (string)


  The name of the Auto Scaling group for the lifecycle hook.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a lifecycle hook**

This example deletes the specified lifecycle hook::

    aws autoscaling delete-lifecycle-hook --lifecycle-hook-name my-lifecycle-hook --auto-scaling-group-name my-auto-scaling-group


======
Output
======

