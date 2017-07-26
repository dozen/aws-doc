[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling create-auto-scaling-group:


*************************
create-auto-scaling-group
*************************



===========
Description
===========



Creates an Auto Scaling group with the specified name and attributes.

 

If you exceed your maximum limit of Auto Scaling groups, which by default is 20 per region, the call fails. For information about viewing and updating this limit, see  describe-account-limits .

 

For more information, see `Auto Scaling Groups <http://docs.aws.amazon.com/autoscaling/latest/userguide/AutoScalingGroup.html>`_ in the *Auto Scaling User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/CreateAutoScalingGroup>`_


========
Synopsis
========

::

    create-auto-scaling-group
  --auto-scaling-group-name <value>
  [--launch-configuration-name <value>]
  [--instance-id <value>]
  --min-size <value>
  --max-size <value>
  [--desired-capacity <value>]
  [--default-cooldown <value>]
  [--availability-zones <value>]
  [--load-balancer-names <value>]
  [--target-group-arns <value>]
  [--health-check-type <value>]
  [--health-check-grace-period <value>]
  [--placement-group <value>]
  [--vpc-zone-identifier <value>]
  [--termination-policies <value>]
  [--new-instances-protected-from-scale-in | --no-new-instances-protected-from-scale-in]
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the group. This name must be unique within the scope of your AWS account.

  

``--launch-configuration-name`` (string)


  The name of the launch configuration. Alternatively, specify an EC2 instance instead of a launch configuration.

  

``--instance-id`` (string)


  The ID of the instance used to create a launch configuration for the group. Alternatively, specify a launch configuration instead of an EC2 instance.

   

  When you specify an ID of an instance, Auto Scaling creates a new launch configuration and associates it with the group. This launch configuration derives its attributes from the specified instance, with the exception of the block device mapping.

   

  For more information, see `Create an Auto Scaling Group Using an EC2 Instance <http://docs.aws.amazon.com/autoscaling/latest/userguide/create-asg-from-instance.html>`_ in the *Auto Scaling User Guide* .

  

``--min-size`` (integer)


  The minimum size of the group.

  

``--max-size`` (integer)


  The maximum size of the group.

  

``--desired-capacity`` (integer)


  The number of EC2 instances that should be running in the group. This number must be greater than or equal to the minimum size of the group and less than or equal to the maximum size of the group.

  

``--default-cooldown`` (integer)


  The amount of time, in seconds, after a scaling activity completes before another scaling activity can start. The default is 300.

   

  For more information, see `Auto Scaling Cooldowns <http://docs.aws.amazon.com/autoscaling/latest/userguide/Cooldown.html>`_ in the *Auto Scaling User Guide* .

  

``--availability-zones`` (list)


  One or more Availability Zones for the group. This parameter is optional if you specify one or more subnets.

  



Syntax::

  "string" "string" ...



``--load-balancer-names`` (list)


  One or more Classic Load Balancers. To specify an Application Load Balancer, use ``target-group-arns`` instead.

   

  For more information, see `Using a Load Balancer With an Auto Scaling Group <http://docs.aws.amazon.com/autoscaling/latest/userguide/create-asg-from-instance.html>`_ in the *Auto Scaling User Guide* .

  



Syntax::

  "string" "string" ...



``--target-group-arns`` (list)


  The Amazon Resource Names (ARN) of the target groups.

  



Syntax::

  "string" "string" ...



``--health-check-type`` (string)


  The service to use for the health checks. The valid values are ``EC2`` and ``ELB`` .

   

  By default, health checks use Amazon EC2 instance status checks to determine the health of an instance. For more information, see `Health Checks <http://docs.aws.amazon.com/autoscaling/latest/userguide/healthcheck.html>`_ in the *Auto Scaling User Guide* .

  

``--health-check-grace-period`` (integer)


  The amount of time, in seconds, that Auto Scaling waits before checking the health status of an EC2 instance that has come into service. During this time, any health check failures for the instance are ignored. The default is 0.

   

  This parameter is required if you are adding an ``ELB`` health check.

   

  For more information, see `Health Checks <http://docs.aws.amazon.com/autoscaling/latest/userguide/healthcheck.html>`_ in the *Auto Scaling User Guide* .

  

``--placement-group`` (string)


  The name of the placement group into which you'll launch your instances, if any. For more information, see `Placement Groups <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--vpc-zone-identifier`` (string)


  A comma-separated list of subnet identifiers for your virtual private cloud (VPC).

   

  If you specify subnets and Availability Zones with this call, ensure that the subnets' Availability Zones match the Availability Zones specified.

   

  For more information, see `Launching Auto Scaling Instances in a VPC <http://docs.aws.amazon.com/autoscaling/latest/userguide/asg-in-vpc.html>`_ in the *Auto Scaling User Guide* .

  

``--termination-policies`` (list)


  One or more termination policies used to select the instance to terminate. These policies are executed in the order that they are listed.

   

  For more information, see `Controlling Which Instances Auto Scaling Terminates During Scale In <http://docs.aws.amazon.com/autoscaling/latest/userguide/as-instance-termination.html>`_ in the *Auto Scaling User Guide* .

  



Syntax::

  "string" "string" ...



``--new-instances-protected-from-scale-in`` | ``--no-new-instances-protected-from-scale-in`` (boolean)


  Indicates whether newly launched instances are protected from termination by Auto Scaling when scaling in.

  

``--tags`` (list)


  One or more tags.

   

  For more information, see `Tagging Auto Scaling Groups and Instances <http://docs.aws.amazon.com/autoscaling/latest/userguide/autoscaling-tagging.html>`_ in the *Auto Scaling User Guide* .

  



Shorthand Syntax::

    ResourceId=string,ResourceType=string,Key=string,Value=string,PropagateAtLaunch=boolean ...




JSON Syntax::

  [
    {
      "ResourceId": "string",
      "ResourceType": "string",
      "Key": "string",
      "Value": "string",
      "PropagateAtLaunch": true|false
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create an Auto Scaling group**

This example creates an Auto Scaling group in a VPC::

    aws autoscaling create-auto-scaling-group --auto-scaling-group-name my-auto-scaling-group --launch-configuration-name my-launch-config --min-size 1 --max-size 3 --vpc-zone-identifier subnet-41767929c

This example creates an Auto Scaling group and configures it to use an Elastic Load Balancing load balancer::

    aws autoscaling create-auto-scaling-group --auto-scaling-group-name my-auto-scaling-group --launch-configuration-name my-launch-config --load-balancer-names my-load-balancer --health-check-type ELB --health-check-grace-period 120

This example creates an Auto Scaling group. It specifies Availability Zones instead of subnets. It also launches instances into a placement group and sets the termination policy to terminate the oldest instances first::

    aws autoscaling create-auto-scaling-group --auto-scaling-group-name my-auto-scaling-group --launch-configuration-name my-launch-config --min-size 1 --max-size 3 --desired-capacity 2 --default-cooldown 600 --placement-group my-placement-group --termination-policies "OldestInstance" --availability-zones us-west-2c

This example creates an Auto Scaling group from the specified EC2 instance and assigns a tag to instances in the group::

    aws autoscaling create-auto-scaling-group --auto-scaling-group-name my-auto-scaling-group --instance-id i-22c99e2a --min-size 1 --max-size 3 --vpc-zone-identifier subnet-41767929 --tags ResourceId=my-auto-scaling-group,ResourceType=auto-scaling-group,Key=Role,Value=WebServer


======
Output
======

None