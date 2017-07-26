[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-instance-attribute:


*************************
modify-instance-attribute
*************************



===========
Description
===========



Modifies the specified attribute of the specified instance. You can specify only one attribute at a time.

 

To modify some attributes, the instance must be stopped. For more information, see `Modifying Attributes of a Stopped Instance`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    modify-instance-attribute
  [--dry-run | --no-dry-run]
  --instance-id <value>
  [--attribute <value>]
  [--value <value>]
  [--block-device-mappings <value>]
  [--source-dest-check | --no-source-dest-check]
  [--disable-api-termination | --no-disable-api-termination]
  [--instance-type <value>]
  [--kernel <value>]
  [--ramdisk <value>]
  [--user-data <value>]
  [--instance-initiated-shutdown-behavior <value>]
  [--groups <value>]
  [--ebs-optimized | --no-ebs-optimized]
  [--sriov-net-support <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instance-id`` (string)


  The ID of the instance.

  

``--attribute`` (string)


  The name of the attribute.

  

  Possible values:

  
  *   ``instanceType``

  
  *   ``kernel``

  
  *   ``ramdisk``

  
  *   ``userData``

  
  *   ``disableApiTermination``

  
  *   ``instanceInitiatedShutdownBehavior``

  
  *   ``rootDeviceName``

  
  *   ``blockDeviceMapping``

  
  *   ``productCodes``

  
  *   ``sourceDestCheck``

  
  *   ``groupSet``

  
  *   ``ebsOptimized``

  
  *   ``sriovNetSupport``

  

  

``--value`` (string)


  A new value for the attribute. Use only with the ``kernel`` , ``ramdisk`` , ``userData`` , ``disableApiTermination`` , or ``instanceInitiatedShutdownBehavior`` attribute.

  

``--block-device-mappings`` (list)


  Modifies the ``DeleteOnTermination`` attribute for volumes that are currently attached. The volume must be owned by the caller. If no value is specified for ``DeleteOnTermination`` , the default is ``true`` and the volume is deleted when the instance is terminated.

   

  To add instance store volumes to an Amazon EBS-backed instance, you must add them when you launch the instance. For more information, see `Updating the Block Device Mapping when Launching an Instance`_ in the *Amazon Elastic Compute Cloud User Guide* .

  



Shorthand Syntax::

    DeviceName=string,Ebs={VolumeId=string,DeleteOnTermination=boolean},VirtualName=string,NoDevice=string ...




JSON Syntax::

  [
    {
      "DeviceName": "string",
      "Ebs": {
        "VolumeId": "string",
        "DeleteOnTermination": true|false
      },
      "VirtualName": "string",
      "NoDevice": "string"
    }
    ...
  ]



``--source-dest-check`` | ``--no-source-dest-check`` (structure)


  Specifies whether source/destination checking is enabled. A value of ``true`` means that checking is enabled, and ``false`` means checking is disabled. This value must be ``false`` for a NAT instance to perform NAT.

  

``--disable-api-termination`` | ``--no-disable-api-termination`` (structure)


  If the value is ``true`` , you can't terminate the instance using the Amazon EC2 console, CLI, or API; otherwise, you can. You cannot use this paramater for Spot Instances.

  

``--instance-type`` (structure)


  Changes the instance type to the specified value. For more information, see `Instance Types`_ . If the instance type is not valid, the error returned is ``InvalidInstanceAttributeValue`` .

  

``--kernel`` (structure)


  Changes the instance's kernel to the specified value. We recommend that you use PV-GRUB instead of kernels and RAM disks. For more information, see `PV-GRUB`_ .

  

``--ramdisk`` (structure)


  Changes the instance's RAM disk to the specified value. We recommend that you use PV-GRUB instead of kernels and RAM disks. For more information, see `PV-GRUB`_ .

  

``--user-data`` (structure)


  Changes the instance's user data to the specified value.

  



Shorthand Syntax::

    Value=blob




JSON Syntax::

  {
    "Value": blob
  }



``--instance-initiated-shutdown-behavior`` (structure)


  Specifies whether an instance stops or terminates when you initiate shutdown from the instance (using the operating system command for system shutdown).

  

``--groups`` (list)


  [EC2-VPC] Changes the security groups of the instance. You must specify at least one security group, even if it's just the default security group for the VPC. You must specify the security group ID, not the security group name.

  



Syntax::

  "string" "string" ...



``--ebs-optimized`` | ``--no-ebs-optimized`` (structure)


  Specifies whether the instance is optimized for EBS I/O. This optimization provides dedicated throughput to Amazon EBS and an optimized configuration stack to provide optimal EBS I/O performance. This optimization isn't available with all instance types. Additional usage charges apply when using an EBS Optimized instance.

  

``--sriov-net-support`` (structure)


  Set to ``simple`` to enable enhanced networking for the instance.

   

  There is no way to disable enhanced networking at this time.

   

  This option is supported only for HVM instances. Specifying this option with a PV instance can make it unreachable.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To modify the instance type**

This example modifies the instance type of the specified instance. The instance must be in the ``stopped`` state. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-instance-attribute --instance-id i-5203422c --instance-type "{\"Value\": \"m1.small\"}"

**To enable enhanced networking on an instance**

This example enables enhanced networking for the specified instance. The instance must be in the ``stopped`` state. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-instance-attribute --instance-id i-1a2b3c4d --sriov-net-support simple

**To modify the sourceDestCheck attribute**

This example sets the ``sourceDestCheck`` attribute of the specified instance to ``true``. The instance must be in a VPC. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-instance-attribute --instance-id i-5203422c --source-dest-check "{\"Value\": true}"

**To modify the deleteOnTermination attribute of the root volume**

This example sets the ``deleteOnTermination`` attribute for the root volume of the specified Amazon EBS-backed instance to ``false``. By default, this attribute is ``true`` for the root volume. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-instance-attribute --instance-id i-5203422c --block-device-mappings "[{\"DeviceName\": \"/dev/sda1\",\"Ebs\":{\"DeleteOnTermination\":false}}]"


======
Output
======

None

.. _Updating the Block Device Mapping when Launching an Instance: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/block-device-mapping-concepts.html#Using_OverridingAMIBDM
.. _Instance Types: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html
.. _Modifying Attributes of a Stopped Instance: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_ChangingAttributesWhileInstanceStopped.html
.. _PV-GRUB: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/UserProvidedKernels.html
