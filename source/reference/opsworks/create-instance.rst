[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks create-instance:


***************
create-instance
***************



===========
Description
===========



Creates an instance in a specified stack. For more information, see `Adding an Instance to a Layer`_ .

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    create-instance
  --stack-id <value>
  --layer-ids <value>
  --instance-type <value>
  [--auto-scaling-type <value>]
  [--hostname <value>]
  [--os <value>]
  [--ami-id <value>]
  [--ssh-key-name <value>]
  [--availability-zone <value>]
  [--virtualization-type <value>]
  [--subnet-id <value>]
  [--architecture <value>]
  [--root-device-type <value>]
  [--block-device-mappings <value>]
  [--install-updates-on-boot | --no-install-updates-on-boot]
  [--ebs-optimized | --no-ebs-optimized]
  [--agent-version <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-id`` (string)


  The stack ID.

  

``--layer-ids`` (list)


  An array that contains the instance's layer IDs.

  



Syntax::

  "string" "string" ...



``--instance-type`` (string)


  The instance type, such as ``t2.micro`` . For a list of supported instance types, open the stack in the console, choose **Instances** , and choose **+ Instance** . The **Size** list contains the currently supported types. For more information, see `Instance Families and Types`_ . The parameter values that you use to specify the various types are in the **API Name** column of the **Available Instance Types** table.

  

``--auto-scaling-type`` (string)


  For load-based or time-based instances, the type. Windows stacks can use only time-based instances.

  

  Possible values:

  
  *   ``load``

  
  *   ``timer``

  

  

``--hostname`` (string)


  The instance host name.

  

``--os`` (string)


  The instance's operating system, which must be set to one of the following.

   

   
  * A supported Linux operating system: An Amazon Linux version, such as ``Amazon Linux 2015.03`` , ``Red Hat Enterprise Linux 7`` , ``Ubuntu 12.04 LTS`` , or ``Ubuntu 14.04 LTS`` .
   
  * ``Microsoft Windows Server 2012 R2 Base`` .
   
  * A custom AMI: ``Custom`` .
   

   

  For more information on the supported operating systems, see `AWS OpsWorks Operating Systems`_ .

   

  The default option is the current Amazon Linux version. If you set this parameter to ``Custom`` , you must use the  create-instance action's AmiId parameter to specify the custom AMI that you want to use. Block device mappings are not supported if the value is ``Custom`` . For more information on the supported operating systems, see `Operating Systems`_ For more information on how to use custom AMIs with AWS OpsWorks, see `Using Custom AMIs`_ .

  

``--ami-id`` (string)


  A custom AMI ID to be used to create the instance. The AMI should be based on one of the supported operating systems. For more information, see `Using Custom AMIs`_ .

   

  .. note::

    If you specify a custom AMI, you must set ``Os`` to ``Custom`` .

  

``--ssh-key-name`` (string)


  The instance's Amazon EC2 key-pair name.

  

``--availability-zone`` (string)


  The instance Availability Zone. For more information, see `Regions and Endpoints`_ .

  

``--virtualization-type`` (string)


  The instance's virtualization type, ``paravirtual`` or ``hvm`` .

  

``--subnet-id`` (string)


  The ID of the instance's subnet. If the stack is running in a VPC, you can use this parameter to override the stack's default subnet ID value and direct AWS OpsWorks to launch the instance in a different subnet. 

  

``--architecture`` (string)


  The instance architecture. The default option is ``x86_64`` . Instance types do not necessarily support both architectures. For a list of the architectures that are supported by the different instance types, see `Instance Families and Types`_ .

  

  Possible values:

  
  *   ``x86_64``

  
  *   ``i386``

  

  

``--root-device-type`` (string)


  The instance root device type. For more information, see `Storage for the Root Device`_ .

  

  Possible values:

  
  *   ``ebs``

  
  *   ``instance-store``

  

  

``--block-device-mappings`` (list)


  An array of ``BlockDeviceMapping`` objects that specify the instance's block devices. For more information, see `Block Device Mapping`_ . Note that block device mappings are not supported for custom AMIs.

  



Shorthand Syntax::

    DeviceName=string,NoDevice=string,VirtualName=string,Ebs={SnapshotId=string,Iops=integer,VolumeSize=integer,VolumeType=string,DeleteOnTermination=boolean} ...




JSON Syntax::

  [
    {
      "DeviceName": "string",
      "NoDevice": "string",
      "VirtualName": "string",
      "Ebs": {
        "SnapshotId": "string",
        "Iops": integer,
        "VolumeSize": integer,
        "VolumeType": "gp2"|"io1"|"standard",
        "DeleteOnTermination": true|false
      }
    }
    ...
  ]



``--install-updates-on-boot`` | ``--no-install-updates-on-boot`` (boolean)


  Whether to install operating system and package updates when the instance boots. The default value is ``true`` . To control when updates are installed, set this value to ``false`` . You must then update your instances manually by using  create-deployment to run the ``update_dependencies`` stack command or by manually running ``yum`` (Amazon Linux) or ``apt-get`` (Ubuntu) on the instances. 

   

  .. note::

     

    We strongly recommend using the default value of ``true`` to ensure that your instances have the latest security updates.

     

  

``--ebs-optimized`` | ``--no-ebs-optimized`` (boolean)


  Whether to create an Amazon EBS-optimized instance.

  

``--agent-version`` (string)


  The default AWS OpsWorks agent version. You have the following options:

   

   
  * ``INHERIT`` - Use the stack's default agent version setting.
   
  * *version_number* - Use the specified agent version. This value overrides the stack's default setting. To update the agent version, edit the instance configuration and specify a new version. AWS OpsWorks then automatically installs that version on the instance.
   

   

  The default setting is ``INHERIT`` . To specify an agent version, you must use the complete version number, not the abbreviated number shown on the console. For a list of available agent version numbers, call  describe-agent-versions .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create an instance**

The following ``create-instance`` command creates an m1.large Amazon Linux instance named myinstance1 in a specified stack.
The instance is assigned to one layer. ::

  aws opsworks --region us-east-1 create-instance --stack-id 935450cc-61e0-4b03-a3e0-160ac817d2bb --layer-ids 5c8c272a-f2d5-42e3-8245-5bf3927cb65b --hostname myinstance1 --instance-type m1.large --os "Amazon Linux"

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

To use an autogenerated name, call `get-hostname-suggestion`_, which generates
a hostname based on the theme that you specified when you created the stack.
Then pass that name to the `hostname` argument.

.. _get-hostname-suggestion: http://docs.aws.amazon.com/cli/latest/reference/opsworks/get-hostname-suggestion.html

*Output*::

  {
    "InstanceId": "5f9adeaa-c94c-42c6-aeef-28a5376002cd"
  }

**More Information**

For more information, see `Adding an Instance to a Layer`_ in the *AWS OpsWorks User Guide*.

.. _`Adding an Instance to a Layer`: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-add.html



======
Output
======

InstanceId -> (string)

  

  The instance ID.

  

  



.. _Block Device Mapping: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/block-device-mapping-concepts.html
.. _Storage for the Root Device: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ComponentsAMIs.html#storage-for-the-root-device
.. _Using Custom AMIs: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-custom-ami.html
.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
.. _AWS OpsWorks Operating Systems: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-os.html
.. _Adding an Instance to a Layer: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-add.html
.. _Regions and Endpoints: http://docs.aws.amazon.com/general/latest/gr/rande.html
.. _Instance Families and Types: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html
.. _Operating Systems: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-os.html
