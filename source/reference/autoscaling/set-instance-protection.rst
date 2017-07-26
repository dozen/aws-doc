[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling set-instance-protection:


***********************
set-instance-protection
***********************



===========
Description
===========



Updates the instance protection settings of the specified instances.

 

For more information, see `Instance Protection`_ in the *Auto Scaling Developer Guide* .



========
Synopsis
========

::

    set-instance-protection
  --instance-ids <value>
  --auto-scaling-group-name <value>
  --protected-from-scale-in | --no-protected-from-scale-in
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-ids`` (list)


  One or more instance IDs.

  



Syntax::

  "string" "string" ...



``--auto-scaling-group-name`` (string)


  The name of the group.

  

``--protected-from-scale-in`` | ``--no-protected-from-scale-in`` (boolean)


  Indicates whether the instance is protected from termination by Auto Scaling when scaling in.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To change the instance protection setting for an instance**

This example enables instance protection for the specified instance::

   aws autoscaling set-instance-protection --instance-ids i-93633f9b --protected-from-scale-in

This example disables instance protection for the specified instance::

   aws autoscaling set-instance-protection --instance-ids i-93633f9b --no-protected-from-scale-in


======
Output
======



.. _Instance Protection: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/AutoScalingBehavior.InstanceTermination.html#instance-protection
