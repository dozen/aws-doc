[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks update-instance:


***************
update-instance
***************



===========
Description
===========



Updates a specified instance.

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    update-instance
  --instance-id <value>
  [--layer-ids <value>]
  [--instance-type <value>]
  [--auto-scaling-type <value>]
  [--hostname <value>]
  [--os <value>]
  [--ami-id <value>]
  [--ssh-key-name <value>]
  [--architecture <value>]
  [--install-updates-on-boot | --no-install-updates-on-boot]
  [--ebs-optimized | --no-ebs-optimized]
  [--agent-version <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-id`` (string)


  The instance ID.

  

``--layer-ids`` (list)


  The instance's layer IDs.

  



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

   

  The default option is the current Amazon Linux version. If you set this parameter to ``Custom`` , you must use the AmiId parameter to specify the custom AMI that you want to use. For more information on the supported operating systems, see `Operating Systems`_ . For more information on how to use custom AMIs with OpsWorks, see `Using Custom AMIs`_ .

   

  .. note::

    You can specify a different Linux operating system for the updated stack, but you cannot change from Linux to Windows or Windows to Linux.

  

``--ami-id`` (string)


  A custom AMI ID to be used to create the instance. The AMI must be based on one of the supported operating systems. For more information, see `Instances`_ 

   

  .. note::

    If you specify a custom AMI, you must set ``Os`` to ``Custom`` .

  

``--ssh-key-name`` (string)


  The instance's Amazon EC2 key name.

  

``--architecture`` (string)


  The instance architecture. Instance types do not necessarily support both architectures. For a list of the architectures that are supported by the different instance types, see `Instance Families and Types`_ .

  

  Possible values:

  
  *   ``x86_64``

  
  *   ``i386``

  

  

``--install-updates-on-boot`` | ``--no-install-updates-on-boot`` (boolean)


  Whether to install operating system and package updates when the instance boots. The default value is ``true`` . To control when updates are installed, set this value to ``false`` . You must then update your instances manually by using  create-deployment to run the ``update_dependencies`` stack command or by manually running ``yum`` (Amazon Linux) or ``apt-get`` (Ubuntu) on the instances. 

   

  .. note::

     

    We strongly recommend using the default value of ``true`` , to ensure that your instances have the latest security updates.

     

  

``--ebs-optimized`` | ``--no-ebs-optimized`` (boolean)


  This property cannot be updated.

  

``--agent-version`` (string)


  The default AWS OpsWorks agent version. You have the following options:

   

   
  * ``INHERIT`` - Use the stack's default agent version setting.
   
  * *version_number* - Use the specified agent version. This value overrides the stack's default setting. To update the agent version, you must edit the instance configuration and specify a new version. AWS OpsWorks then automatically installs that version on the instance.
   

   

  The default setting is ``INHERIT`` . To specify an agent version, you must use the complete version number, not the abbreviated number shown on the console. For a list of available agent version numbers, call  describe-agent-versions .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To update an instance**

The following example updates a specified instance's type. ::

  aws opsworks --region us-east-1 update-instance --instance-id dfe18b02-5327-493d-91a4-c5c0c448927f --instance-type c3.xlarge

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: None.

**More Information**

For more information, see `Editing the Instance Configuration`_ in the *AWS OpsWorks User Guide*.

.. _`Editing the Instance Configuration`: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-properties.html



======
Output
======

None

.. _Using Custom AMIs: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-custom-ami.html
.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
.. _Instances: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-custom-ami.html
.. _AWS OpsWorks Operating Systems: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-os.html
.. _Instance Families and Types: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html
.. _Operating Systems: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-os.html
