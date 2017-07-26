[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling create-launch-configuration:


***************************
create-launch-configuration
***************************



===========
Description
===========



Creates a launch configuration.

 

If you exceed your maximum limit of launch configurations, which by default is 100 per region, the call fails. For information about viewing and updating this limit, see  describe-account-limits .

 

For more information, see `Launch Configurations <http://docs.aws.amazon.com/autoscaling/latest/userguide/LaunchConfiguration.html>`_ in the *Auto Scaling User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/CreateLaunchConfiguration>`_


========
Synopsis
========

::

    create-launch-configuration
  --launch-configuration-name <value>
  [--image-id <value>]
  [--key-name <value>]
  [--security-groups <value>]
  [--classic-link-vpc-id <value>]
  [--classic-link-vpc-security-groups <value>]
  [--user-data <value>]
  [--instance-id <value>]
  [--instance-type <value>]
  [--kernel-id <value>]
  [--ramdisk-id <value>]
  [--block-device-mappings <value>]
  [--instance-monitoring <value>]
  [--spot-price <value>]
  [--iam-instance-profile <value>]
  [--ebs-optimized | --no-ebs-optimized]
  [--associate-public-ip-address | --no-associate-public-ip-address]
  [--placement-tenancy <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--launch-configuration-name`` (string)


  The name of the launch configuration. This name must be unique within the scope of your AWS account.

  

``--image-id`` (string)


  The ID of the Amazon Machine Image (AMI) to use to launch your EC2 instances. For more information, see `Finding an AMI <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/finding-an-ami.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--key-name`` (string)


  The name of the key pair. For more information, see `Amazon EC2 Key Pairs <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--security-groups`` (list)


  One or more security groups with which to associate the instances.

   

  If your instances are launched in EC2-Classic, you can either specify security group names or the security group IDs. For more information about security groups for EC2-Classic, see `Amazon EC2 Security Groups <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-network-security.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

   

  If your instances are launched into a VPC, specify security group IDs. For more information, see `Security Groups for Your VPC <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_SecurityGroups.html>`_ in the *Amazon Virtual Private Cloud User Guide* .

  



Syntax::

  "string" "string" ...



``--classic-link-vpc-id`` (string)


  The ID of a ClassicLink-enabled VPC to link your EC2-Classic instances to. This parameter is supported only if you are launching EC2-Classic instances. For more information, see `ClassicLink <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/vpc-classiclink.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--classic-link-vpc-security-groups`` (list)


  The IDs of one or more security groups for the specified ClassicLink-enabled VPC. This parameter is required if you specify a ClassicLink-enabled VPC, and is not supported otherwise. For more information, see `ClassicLink <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/vpc-classiclink.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

  



Syntax::

  "string" "string" ...



``--user-data`` (string)


  The user data to make available to the launched EC2 instances. For more information, see `Instance Metadata and User Data <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--instance-id`` (string)


  The ID of the instance to use to create the launch configuration.

   

  The new launch configuration derives attributes from the instance, with the exception of the block device mapping.

   

  To create a launch configuration with a block device mapping or override any other instance attributes, specify them as part of the same request.

   

  For more information, see `Create a Launch Configuration Using an EC2 Instance <http://docs.aws.amazon.com/autoscaling/latest/userguide/create-lc-with-instanceID.html>`_ in the *Auto Scaling User Guide* .

  

``--instance-type`` (string)


  The instance type of the EC2 instance. For information about available instance types, see `Available Instance Types <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html#AvailableInstanceTypes>`_ in the *Amazon Elastic Compute Cloud User Guide.*  

  

``--kernel-id`` (string)


  The ID of the kernel associated with the AMI.

  

``--ramdisk-id`` (string)


  The ID of the RAM disk associated with the AMI.

  

``--block-device-mappings`` (list)


  One or more mappings that specify how block devices are exposed to the instance. For more information, see `Block Device Mapping <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/block-device-mapping-concepts.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

  



Shorthand Syntax::

    VirtualName=string,DeviceName=string,Ebs={SnapshotId=string,VolumeSize=integer,VolumeType=string,DeleteOnTermination=boolean,Iops=integer,Encrypted=boolean},NoDevice=boolean ...




JSON Syntax::

  [
    {
      "VirtualName": "string",
      "DeviceName": "string",
      "Ebs": {
        "SnapshotId": "string",
        "VolumeSize": integer,
        "VolumeType": "string",
        "DeleteOnTermination": true|false,
        "Iops": integer,
        "Encrypted": true|false
      },
      "NoDevice": true|false
    }
    ...
  ]



``--instance-monitoring`` (structure)


  Enables detailed monitoring (``true`` ) or basic monitoring (``false`` ) for the Auto Scaling instances.

  



Shorthand Syntax::

    Enabled=boolean




JSON Syntax::

  {
    "Enabled": true|false
  }



``--spot-price`` (string)


  The maximum hourly price to be paid for any Spot Instance launched to fulfill the request. Spot Instances are launched when the price you specify exceeds the current Spot market price. For more information, see `Launching Spot Instances in Your Auto Scaling Group <http://docs.aws.amazon.com/autoscaling/latest/userguide/US-SpotInstances.html>`_ in the *Auto Scaling User Guide* .

  

``--iam-instance-profile`` (string)


  The name or the Amazon Resource Name (ARN) of the instance profile associated with the IAM role for the instance.

   

  EC2 instances launched with an IAM role will automatically have AWS security credentials available. You can use IAM roles with Auto Scaling to automatically enable applications running on your EC2 instances to securely access other AWS resources. For more information, see `Launch Auto Scaling Instances with an IAM Role <http://docs.aws.amazon.com/autoscaling/latest/userguide/us-iam-role.html>`_ in the *Auto Scaling User Guide* .

  

``--ebs-optimized`` | ``--no-ebs-optimized`` (boolean)


  Indicates whether the instance is optimized for Amazon EBS I/O. By default, the instance is not optimized for EBS I/O. The optimization provides dedicated throughput to Amazon EBS and an optimized configuration stack to provide optimal I/O performance. This optimization is not available with all instance types. Additional usage charges apply. For more information, see `Amazon EBS-Optimized Instances <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSOptimized.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--associate-public-ip-address`` | ``--no-associate-public-ip-address`` (boolean)


  Used for groups that launch instances into a virtual private cloud (VPC). Specifies whether to assign a public IP address to each instance. For more information, see `Launching Auto Scaling Instances in a VPC <http://docs.aws.amazon.com/autoscaling/latest/userguide/asg-in-vpc.html>`_ in the *Auto Scaling User Guide* .

   

  If you specify this parameter, be sure to specify at least one subnet when you create your group.

   

  Default: If the instance is launched into a default subnet, the default is ``true`` . If the instance is launched into a nondefault subnet, the default is ``false`` . For more information, see `Supported Platforms <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-supported-platforms.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--placement-tenancy`` (string)


  The tenancy of the instance. An instance with a tenancy of ``dedicated`` runs on single-tenant hardware and can only be launched into a VPC.

   

  You must set the value of this parameter to ``dedicated`` if want to launch Dedicated Instances into a shared tenancy VPC (VPC with instance placement tenancy attribute set to ``default`` ).

   

  If you specify this parameter, be sure to specify at least one subnet when you create your group.

   

  For more information, see `Launching Auto Scaling Instances in a VPC <http://docs.aws.amazon.com/autoscaling/latest/userguide/asg-in-vpc.html>`_ in the *Auto Scaling User Guide* .

   

  Valid values: ``default`` | ``dedicated``  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a launch configuration**

This example creates a launch configuration::

    aws autoscaling create-launch-configuration --launch-configuration-name my-launch-config --image-id ami-c6169af6 --instance-type m1.medium

This example creates a launch configuration that uses Spot Instances::

    aws autoscaling create-launch-configuration --launch-configuration-name my-launch-config --image-id ami-c6169af6 --instance-type m1.medium --spot-price "0.50"

This example creates a launch configuration with a key pair and a bootstrapping script::

    aws autoscaling create-launch-configuration --launch-configuration-name my-launch-config --key-name my-key-pair --image-id ami-c6169af6 --instance-type m1.small --user-data file://myuserdata.txt

This example creates a launch configuration based on an existing instance. In addition, it also specifies launch configuration attributes such as a security group, tenancy, Amazon EBS optimization, and a bootstrapping script::

    aws autoscaling create-launch-configuration --launch-configuration-name my-launch-config --key-name my-key-pair --instance-id i-7e13c876 --security-groups sg-eb2af88e --instance-type m1.small --user-data file://myuserdata.txt --instance-monitoring Enabled=true --no-ebs-optimized --no-associate-public-ip-address --placement-tenancy dedicated --iam-instance-profile my-autoscaling-role

Add the following parameter to add an Amazon EBS volume with the device name ``/dev/sdh`` and a volume size of 100.

Parameter::

    --block-device-mappings "[{\"DeviceName\": \"/dev/sdh\",\"Ebs\":{\"VolumeSize\":100}}]"

Add the following parameter to add ``ephemeral1`` as an instance store volume with the device name ``/dev/sdc``.

Parameter::

    --block-device-mappings "[{\"DeviceName\": \"/dev/sdc\",\"VirtualName\":\"ephemeral1\"}]"

Add the following parameter to omit a device included on the instance (for example, ``/dev/sdf``).

Parameter::

    --block-device-mappings "[{\"DeviceName\": \"/dev/sdf\",\"NoDevice\":\"\"}]"


======
Output
======

None