[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling attach-instances:


****************
attach-instances
****************



===========
Description
===========



Attaches one or more EC2 instances to the specified Auto Scaling group.

 

When you attach instances, Auto Scaling increases the desired capacity of the group by the number of instances being attached. If the number of instances being attached plus the desired capacity of the group exceeds the maximum size of the group, the operation fails.

 

If there is a Classic Load Balancer attached to your Auto Scaling group, the instances are also registered with the load balancer. If there are target groups attached to your Auto Scaling group, the instances are also registered with the target groups.

 

For more information, see `Attach EC2 Instances to Your Auto Scaling Group <http://docs.aws.amazon.com/autoscaling/latest/userguide/attach-instance-asg.html>`_ in the *Auto Scaling User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/AttachInstances>`_


========
Synopsis
========

::

    attach-instances
  [--instance-ids <value>]
  --auto-scaling-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-ids`` (list)


  One or more instance IDs.

  



Syntax::

  "string" "string" ...



``--auto-scaling-group-name`` (string)


  The name of the group.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To attach an instance to an Auto Scaling group**

This example attaches the specified instance to the specified Auto Scaling group::

    aws autoscaling attach-instances --instance-ids i-93633f9b --auto-scaling-group-name my-auto-scaling-group


======
Output
======

None