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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DeletePolicy>`_


========
Synopsis
========

::

    delete-policy
  [--auto-scaling-group-name <value>]
  --policy-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the Auto Scaling group.

  

``--policy-name`` (string)


  The name or Amazon Resource Name (ARN) of the policy.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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