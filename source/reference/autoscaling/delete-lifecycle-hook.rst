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



========
Synopsis
========

::

    delete-lifecycle-hook
  --lifecycle-hook-name <value>
  --auto-scaling-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--lifecycle-hook-name`` (string)


  The name of the lifecycle hook.

  

``--auto-scaling-group-name`` (string)


  The name of the Auto Scaling group for the lifecycle hook.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a lifecycle hook**

This example deletes the specified lifecycle hook::

   aws autoscaling delete-lifecycle-hook --lifecycle-hook-name my-lifecycle-hook --auto-scaling-group-name my-auto-scaling-group


======
Output
======

