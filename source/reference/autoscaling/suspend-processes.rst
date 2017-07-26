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

 

For more information, see `Suspending and Resuming Auto Scaling Processes`_ in the *Auto Scaling Developer Guide* .



========
Synopsis
========

::

    suspend-processes
  --auto-scaling-group-name <value>
  [--scaling-processes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name or Amazon Resource Name (ARN) of the Auto Scaling group.

  

``--scaling-processes`` (list)


  One or more of the following processes:

   

   
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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

.. _Suspending and Resuming Auto Scaling Processes: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/US_SuspendResume.html
