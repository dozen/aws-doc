[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling delete-policy:


*************
delete-policy
*************



===========
Description
===========



Deletes the specified Auto Scaling policy.

 

Deleting a policy deletes the underlying alarm action, but does not delete the alarm, even if it no longer has an associated action.



========
Synopsis
========

::

    delete-policy
  [--auto-scaling-group-name <value>]
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the Auto Scaling group.

  

``--policy-name`` (string)


  The name or Amazon Resource Name (ARN) of the policy.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete an Auto Scaling policy**

This example deletes the specified Auto Scaling policy::

	aws autoscaling delete-policy --auto-scaling-group-name my-auto-scaling-group --policy-name ScaleIn


======
Output
======

None