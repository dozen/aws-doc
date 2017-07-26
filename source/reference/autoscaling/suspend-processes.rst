[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling suspend-processes:


*****************
suspend-processes
*****************



===========
Description
===========



Suspends the specified Auto Scaling processes, or all processes, for the specified Auto Scaling group.

 

Note that if you suspend either the ``Launch`` or ``Terminate`` process types, it can prevent other process types from functioning properly.

 

To resume processes that have been suspended, use  resume-processes .

 

For more information, see `Suspending and Resuming Auto Scaling Processes <http://docs.aws.amazon.com/autoscaling/latest/userguide/as-suspend-resume-processes.html>`_ in the *Auto Scaling User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/SuspendProcesses>`_


========
Synopsis
========

::

    suspend-processes
  --auto-scaling-group-name <value>
  [--scaling-processes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name or Amazon Resource Name (ARN) of the Auto Scaling group.

  

``--scaling-processes`` (list)


  One or more of the following processes. If you omit this parameter, all processes are specified.

   

   
  * ``Launch``   
   
  * ``Terminate``   
   
  * ``HealthCheck``   
   
  * ``ReplaceUnhealthy``   
   
  * ``AZRebalance``   
   
  * ``AlarmNotification``   
   
  * ``ScheduledActions``   
   
  * ``AddToLoadBalancer``   
   

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To suspend Auto Scaling processes**

This example suspends the specified scaling process for the specified Auto Scaling group::

    aws autoscaling suspend-processes --auto-scaling-group-name my-auto-scaling-group --scaling-processes AlarmNotification

For more information, see `Suspend and Resume Auto Scaling Processes`_ in the *Auto Scaling Developer Guide*.

.. _`Suspend and Resume Auto Scaling Processes`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/US_SuspendResume.html


======
Output
======

None