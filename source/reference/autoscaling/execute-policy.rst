[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling execute-policy:


**************
execute-policy
**************



===========
Description
===========



Executes the specified policy.



========
Synopsis
========

::

    execute-policy
  [--auto-scaling-group-name <value>]
  --policy-name <value>
  [--honor-cooldown | --no-honor-cooldown]
  [--metric-value <value>]
  [--breach-threshold <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name or Amazon Resource Name (ARN) of the Auto Scaling group.

  

``--policy-name`` (string)


  The name or ARN of the policy.

  

``--honor-cooldown`` | ``--no-honor-cooldown`` (boolean)


  If this parameter is true, Auto Scaling waits for the cooldown period to complete before executing the policy. Otherwise, Auto Scaling executes the policy without waiting for the cooldown period to complete.

   

  This parameter is not supported if the policy type is ``StepScaling`` .

   

  For more information, see `Auto Scaling Cooldowns`_ in the *Auto Scaling Developer Guide* .

  

``--metric-value`` (double)


  The metric value to compare to ``BreachThreshold`` . This enables you to execute a policy of type ``StepScaling`` and determine which step adjustment to use. For example, if the breach threshold is 50 and you want to use a step adjustment with a lower bound of 0 and an upper bound of 10, you can set the metric value to 59.

   

  If you specify a metric value that doesn't correspond to a step adjustment for the policy, the call returns an error.

   

  This parameter is required if the policy type is ``StepScaling`` and not supported otherwise.

  

``--breach-threshold`` (double)


  The breach threshold for the alarm.

   

  This parameter is required if the policy type is ``StepScaling`` and not supported otherwise.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To execute an Auto Scaling policy**

This example executes the specified Auto Scaling policy for the specified Auto Scaling group::

	aws autoscaling execute-policy --auto-scaling-group-name my-auto-scaling-group --policy-name ScaleIn --honor-cooldown

For more information, see `Dynamic Scaling`_ in the *Auto Scaling Developer Guide*.

.. _`Dynamic Scaling`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-scale-based-on-demand.html


======
Output
======

None

.. _Auto Scaling Cooldowns: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/Cooldown.html
