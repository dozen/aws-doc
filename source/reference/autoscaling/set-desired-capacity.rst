[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling set-desired-capacity:


********************
set-desired-capacity
********************



===========
Description
===========



Sets the size of the specified Auto Scaling group.

 

For more information about desired capacity, see `What Is Auto Scaling? <http://docs.aws.amazon.com/autoscaling/latest/userguide/WhatIsAutoScaling.html>`_ in the *Auto Scaling User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/SetDesiredCapacity>`_


========
Synopsis
========

::

    set-desired-capacity
  --auto-scaling-group-name <value>
  --desired-capacity <value>
  [--honor-cooldown | --no-honor-cooldown]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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