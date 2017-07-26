[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling delete-auto-scaling-group:


*************************
delete-auto-scaling-group
*************************



===========
Description
===========



Deletes the specified Auto Scaling group.

 

If the group has instances or scaling activities in progress, you must specify the option to force the deletion in order for it to succeed.

 

If the group has policies, deleting the group deletes the policies, the underlying alarm actions, and any alarm that no longer has an associated action.

 

To remove instances from the Auto Scaling group before deleting it, call  detach-instances with the list of instances and the option to decrement the desired capacity so that Auto Scaling does not launch replacement instances.

 

To terminate all instances before deleting the Auto Scaling group, call  update-auto-scaling-group and set the minimum size and desired capacity of the Auto Scaling group to zero.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DeleteAutoScalingGroup>`_


========
Synopsis
========

::

    delete-auto-scaling-group
  --auto-scaling-group-name <value>
  [--force-delete | --no-force-delete]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the group to delete.

  

``--force-delete`` | ``--no-force-delete`` (boolean)


  Specifies that the group will be deleted along with all instances associated with the group, without waiting for all instances to be terminated. This parameter also deletes any lifecycle actions associated with the group.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete an Auto Scaling group**

This example deletes the specified Auto Scaling group::

    aws autoscaling delete-auto-scaling-group --auto-scaling-group-name my-auto-scaling-group

To delete the Auto Scaling group without waiting for the instances in the group to terminate, use the ``--force-delete`` parameter::

    aws autoscaling delete-auto-scaling-group --auto-scaling-group-name my-auto-scaling-group --force-delete

For more information, see `Shut Down Auto Scaling Processes`_ in the *Auto Scaling Developer Guide*.

.. _`Shut Down Auto Scaling Processes`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-process-shutdown.html


======
Output
======

None