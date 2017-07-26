[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-instance-attribute:


*************************
modify-instance-attribute
*************************



===========
Description
===========



Modifies the specified attribute of the specified instance. You can specify only one attribute at a time.

 

To modify some attributes, the instance must be stopped. For more information, see `Modifying Attributes of a Stopped Instance <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_ChangingAttributesWhileInstanceStopped.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ModifyInstanceAttribute>`_


========
Synopsis
========

::

    modify-instance-attribute
  [--source-dest-check | --no-source-dest-check]
  [--attribute <value>]
  [--block-device-mappings <value>]
  [--disable-api-termination | --no-disable-api-termination]
  [--dry-run | --no-dry-run]
  [--ebs-optimized | --no-ebs-optimized]
  [--ena-support | --no-ena-support]
  [--groups <value>]
  --instance-id <value>
  [--instance-initiated-shutdown-behavior <value>]
  [--instance-type <value>]
  [--kernel <value>]
  [--ramdisk <value>]
  [--sriov-net-support <value>]
  [--user-data <value>]
  [--value <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--source-dest-check`` | ``--no-source-dest-check`` (structure)


  Specifies whether source/destination checking is enabled. A value of ``true`` means that checking is enabled, and ``false`` means checking is disabled. This value must be ``false`` for a NAT instance to perform NAT.

  

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

  
  *   ``enaSupport``

  

  

``--block-device-mappings`` (list)


  Modifies the ``DeleteOnTermination`` attribute for volumes that are currently attached. The volume must be owned by the caller. If no value is specified for ``DeleteOnTermination`` , the default is ``true`` and the volume is deleted when the instance is terminated.

   

  To add instance store volumes to an Amazon EBS-backed instance, you must add them when you launch the instance. For more information, see `Updating the Block Device Mapping when Launching an Instance <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/block-device-mapping-concepts.html#Using_OverridingAMIBDM>`_ in the *Amazon Elastic Compute Cloud User Guide* .

  



Shorthand Syntax::

    DeviceName=string,Ebs={DeleteOnTermination=boolean,VolumeId=string},NoDevice=string,VirtualName=string ...




JSON Syntax::

  [
    {
      "DeviceName": "string",
      "Ebs": {
        "DeleteOnTermination": true|false,
        "VolumeId": "string"
      },
      "NoDevice": "string",
      "VirtualName": "string"
    }
    ...
  ]



``--disable-api-termination`` | ``--no-disable-api-termination`` (structure)


  If the value is ``true`` , you can't terminate the instance using the Amazon EC2 console, CLI, or API; otherwise, you can. You cannot use this parameter for Spot Instances.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--ebs-optimized`` | ``--no-ebs-optimized`` (structure)


  Specifies whether the instance is optimized for EBS I/O. This optimization provides dedicated throughput to Amazon EBS and an optimized configuration stack to provide optimal EBS I/O performance. This optimization isn't available with all instance types. Additional usage charges apply when using an EBS Optimized instance.

  

``--ena-support`` | ``--no-ena-support`` (structure)


  Set to ``true`` to enable enhanced networking with ENA for the instance.

   

  This option is supported only for HVM instances. Specifying this option with a PV instance can make it unreachable.

  

``--groups`` (list)


  [EC2-VPC] Changes the security groups of the instance. You must specify at least one security group, even if it's just the default security group for the VPC. You must specify the security group ID, not the security group name.

  



Syntax::

  "string" "string" ...



``--instance-id`` (string)


  The ID of the instance.

  

``--instance-initiated-shutdown-behavior`` (structure)


  Specifies whether an instance stops or terminates when you initiate shutdown from the instance (using the operating system command for system shutdown).

  

``--instance-type`` (structure)


  Changes the instance type to the specified value. For more information, see `Instance Types <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html>`_ . If the instance type is not valid, the error returned is ``InvalidInstanceAttributeValue`` .

  

``--kernel`` (structure)


  Changes the instance's kernel to the specified value. We recommend that you use PV-GRUB instead of kernels and RAM disks. For more information, see `PV-GRUB <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/UserProvidedKernels.html>`_ .

  

``--ramdisk`` (structure)


  Changes the instance's RAM disk to the specified value. We recommend that you use PV-GRUB instead of kernels and RAM disks. For more information, see `PV-GRUB <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/UserProvidedKernels.html>`_ .

  

``--sriov-net-support`` (structure)


  Set to ``simple`` to enable enhanced networking with the Intel 82599 Virtual Function interface for the instance.

   

  There is no way to disable enhanced networking with the Intel 82599 Virtual Function interface at this time.

   

  This option is supported only for HVM instances. Specifying this option with a PV instance can make it unreachable.

  

``--user-data`` (structure)


  Changes the instance's user data to the specified value. If you are using an AWS SDK or command line tool, Base64-encoding is performed for you, and you can load the text from a file. Otherwise, you must provide Base64-encoded text.

  



Shorthand Syntax::

    Value=blob




JSON Syntax::

  {
    "Value": blob
  }



``--value`` (string)


  A new value for the attribute. Use only with the ``kernel`` , ``ramdisk`` , ``userData`` , ``disableApiTermination`` , or ``instanceInitiatedShutdownBehavior`` attribute.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To modify the instance type**

This example modifies the instance type of the specified instance. The instance must be in the ``stopped`` state. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-instance-attribute --instance-id i-1234567890abcdef0 --instance-type "{\"Value\": \"m1.small\"}"

**To enable enhanced networking on an instance**

This example enables enhanced networking for the specified instance. The instance must be in the ``stopped`` state. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-instance-attribute --instance-id i-1234567890abcdef0 --sriov-net-support simple

**To modify the sourceDestCheck attribute**

This example sets the ``sourceDestCheck`` attribute of the specified instance to ``true``. The instance must be in a VPC. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-instance-attribute --instance-id i-1234567890abcdef0 --source-dest-check "{\"Value\": true}"

**To modify the deleteOnTermination attribute of the root volume**

This example sets the ``deleteOnTermination`` attribute for the root volume of the specified Amazon EBS-backed instance to ``false``. By default, this attribute is ``true`` for the root volume. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-instance-attribute --instance-id i-1234567890abcdef0 --block-device-mappings "[{\"DeviceName\": \"/dev/sda1\",\"Ebs\":{\"DeleteOnTermination\":false}}]"


======
Output
======

None