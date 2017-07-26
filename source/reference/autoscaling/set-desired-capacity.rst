[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling set-desired-capacity:


********************
set-desired-capacity
********************



===========
Description
===========



Sets the size of the specified Auto Scaling group.

 

For more information about desired capacity, see `What Is Auto Scaling?`_ in the *Auto Scaling Developer Guide* .



========
Synopsis
========

::

    set-desired-capacity
  --auto-scaling-group-name <value>
  --desired-capacity <value>
  [--honor-cooldown | --no-honor-cooldown]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the Auto Scaling group.

  

``--desired-capacity`` (integer)


  The number of EC2 instances that should be running in the Auto Scaling group.

  

``--honor-cooldown`` | ``--no-honor-cooldown`` (boolean)


  By default, ``set-desired-capacity`` overrides any cooldown period associated with the Auto Scaling group. Specify ``True`` to make Auto Scaling to wait for the cool-down period associated with the Auto Scaling group to complete before initiating a scaling activity to set your Auto Scaling group to its new capacity.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To set the desired capacity for an Auto Scaling group**

This example sets the desired capacity for the specified Auto Scaling group::

	aws autoscaling set-desired-capacity --auto-scaling-group-name my-auto-scaling-group --desired-capacity 2 --honor-cooldown


======
Output
======

None

.. _What Is Auto Scaling?: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/WhatIsAutoScaling.html
