[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling update-auto-scaling-group:


*************************
update-auto-scaling-group
*************************



===========
Description
===========



Updates the configuration for the specified Auto Scaling group.

 

To update an Auto Scaling group with a launch configuration with ``InstanceMonitoring`` set to ``False`` , you must first disable the collection of group metrics. Otherwise, you will get an error. If you have previously enabled the collection of group metrics, you can disable it using  disable-metrics-collection .

 

The new settings are registered upon the completion of this call. Any launch configuration settings take effect on any triggers after this call returns. Scaling activities that are currently in progress aren't affected.

 

Note the following:

 

 
* If you specify a new value for ``MinSize`` without specifying a value for ``DesiredCapacity`` , and the new ``MinSize`` is larger than the current size of the group, we implicitly call  set-desired-capacity to set the size of the group to the new value of ``MinSize`` . 
 
* If you specify a new value for ``MaxSize`` without specifying a value for ``DesiredCapacity`` , and the new ``MaxSize`` is smaller than the current size of the group, we implicitly call  set-desired-capacity to set the size of the group to the new value of ``MaxSize`` . 
 
* All other optional parameters are left unchanged if not specified. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/UpdateAutoScalingGroup>`_


========
Synopsis
========

::

    update-auto-scaling-group
  --auto-scaling-group-name <value>
  [--launch-configuration-name <value>]
  [--min-size <value>]
  [--max-size <value>]
  [--desired-capacity <value>]
  [--default-cooldown <value>]
  [--availability-zones <value>]
  [--health-check-type <value>]
  [--health-check-grace-period <value>]
  [--placement-group <value>]
  [--vpc-zone-identifier <value>]
  [--termination-policies <value>]
  [--new-instances-protected-from-scale-in | --no-new-instances-protected-from-scale-in]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the Auto Scaling group.

  

``--launch-configuration-name`` (string)


  The name of the launch configuration.

  

``--min-size`` (integer)


  The minimum size of the Auto Scaling group.

  

``--max-size`` (integer)


  The maximum size of the Auto Scaling group.

  

``--desired-capacity`` (integer)


  The number of EC2 instances that should be running in the Auto Scaling group. This number must be greater than or equal to the minimum size of the group and less than or equal to the maximum size of the group.

  

``--default-cooldown`` (integer)


  The amount of time, in seconds, after a scaling activity completes before another scaling activity can start. The default is 300.

   

  For more information, see `Auto Scaling Cooldowns <http://docs.aws.amazon.com/autoscaling/latest/userguide/Cooldown.html>`_ in the *Auto Scaling User Guide* .

  

``--availability-zones`` (list)


  One or more Availability Zones for the group.

  



Syntax::

  "string" "string" ...



``--health-check-type`` (string)


  The service to use for the health checks. The valid values are ``EC2`` and ``ELB`` .

  

``--health-check-grace-period`` (integer)


  The amount of time, in seconds, that Auto Scaling waits before checking the health status of an EC2 instance that has come into service. The default is 0.

   

  For more information, see `Health Checks <http://docs.aws.amazon.com/autoscaling/latest/userguide/healthcheck.html>`_ in the *Auto Scaling User Guide* .

  

``--placement-group`` (string)


  The name of the placement group into which you'll launch your instances, if any. For more information, see `Placement Groups <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--vpc-zone-identifier`` (string)


  The ID of the subnet, if you are launching into a VPC. You can specify several subnets in a comma-separated list.

   

  When you specify ``VPCZoneIdentifier`` with ``availability-zones`` , ensure that the subnets' Availability Zones match the values you specify for ``availability-zones`` .

   

  For more information, see `Launching Auto Scaling Instances in a VPC <http://docs.aws.amazon.com/autoscaling/latest/userguide/asg-in-vpc.html>`_ in the *Auto Scaling User Guide* .

  

``--termination-policies`` (list)


  A standalone termination policy or a list of termination policies used to select the instance to terminate. The policies are executed in the order that they are listed.

   

  For more information, see `Controlling Which Instances Auto Scaling Terminates During Scale In <http://docs.aws.amazon.com/autoscaling/latest/userguide/as-instance-termination.html>`_ in the *Auto Scaling User Guide* .

  



Syntax::

  "string" "string" ...



``--new-instances-protected-from-scale-in`` | ``--no-new-instances-protected-from-scale-in`` (boolean)


  Indicates whether newly launched instances are protected from termination by Auto Scaling when scaling in.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To update an Auto Scaling group**

This example updates the specified Auto Scaling group to use Elastic Load Balancing health checks::

    aws autoscaling update-auto-scaling-group --auto-scaling-group-name my-auto-scaling-group --health-check-type ELB --health-check-grace-period 60

This example updates the launch configuration, minimum and maximum size of the group, and which subnet to use::

    aws autoscaling update-auto-scaling-group --auto-scaling-group-name my-auto-scaling-group --launch-configuration-name new-launch-config --min-size 1 --max-size 3 --vpc-zone-identifier subnet-41767929

This example updates the desired capacity, default cooldown, placement group, termination policy, and which Availability Zone to use::

    aws autoscaling update-auto-scaling-group --auto-scaling-group-name my-auto-scaling-group --default-cooldown 600 --placement-group my-placement-group --termination-policies "OldestInstance" --availability-zones us-west-2c

This example enables the instance protection setting for the specified Auto Scaling group::

    aws autoscaling update-auto-scaling-group --auto-scaling-group-name my-auto-scaling-group --new-instances-protected-from-scale-in

This example disables the instance protection setting for the specified Auto Scaling group::

    aws autoscaling update-auto-scaling-group --auto-scaling-group-name my-auto-scaling-group --no-new-instances-protected-from-scale-in


======
Output
======

None