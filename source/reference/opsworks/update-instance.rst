[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks update-instance:


***************
update-instance
***************



===========
Description
===========



Updates a specified instance.

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/UpdateInstance>`_


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
  [--generate-cli-skeleton <value>]




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


  The instance type, such as ``t2.micro`` . For a list of supported instance types, open the stack in the console, choose **Instances** , and choose **+ Instance** . The **Size** list contains the currently supported types. For more information, see `Instance Families and Types <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html>`_ . The parameter values that you use to specify the various types are in the **API Name** column of the **Available Instance Types** table.

  

``--auto-scaling-type`` (string)


  For load-based or time-based instances, the type. Windows stacks can use only time-based instances.

  

  Possible values:

  
  *   ``load``

  
  *   ``timer``

  

  

``--hostname`` (string)


  The instance host name.

  

``--os`` (string)


  The instance's operating system, which must be set to one of the following. You cannot update an instance that is using a custom AMI.

   

   
  * A supported Linux operating system: An Amazon Linux version, such as ``Amazon Linux 2017.03`` , ``Amazon Linux 2016.09`` , ``Amazon Linux 2016.03`` , ``Amazon Linux 2015.09`` , or ``Amazon Linux 2015.03`` . 
   
  * A supported Ubuntu operating system, such as ``Ubuntu 16.04 LTS`` , ``Ubuntu 14.04 LTS`` , or ``Ubuntu 12.04 LTS`` . 
   
  * ``CentOS Linux 7``   
   
  * ``Red Hat Enterprise Linux 7``   
   
  * A supported Windows operating system, such as ``Microsoft Windows Server 2012 R2 Base`` , ``Microsoft Windows Server 2012 R2 with SQL Server Express`` , ``Microsoft Windows Server 2012 R2 with SQL Server Standard`` , or ``Microsoft Windows Server 2012 R2 with SQL Server Web`` . 
   

   

  For more information on the supported operating systems, see `AWS OpsWorks Stacks Operating Systems <http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-os.html>`_ .

   

  The default option is the current Amazon Linux version. If you set this parameter to ``Custom`` , you must use the AmiId parameter to specify the custom AMI that you want to use. For more information on the supported operating systems, see `Operating Systems <http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-os.html>`_ . For more information on how to use custom AMIs with OpsWorks, see `Using Custom AMIs <http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-custom-ami.html>`_ .

   

  .. note::

     

    You can specify a different Linux operating system for the updated stack, but you cannot change from Linux to Windows or Windows to Linux.

     

  

``--ami-id`` (string)


  The ID of the AMI that was used to create the instance. The value of this parameter must be the same AMI ID that the instance is already using. You cannot apply a new AMI to an instance by running UpdateInstance. update-instance does not work on instances that are using custom AMIs. 

  

``--ssh-key-name`` (string)


  The instance's Amazon EC2 key name.

  

``--architecture`` (string)


  The instance architecture. Instance types do not necessarily support both architectures. For a list of the architectures that are supported by the different instance types, see `Instance Families and Types <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html>`_ .

  

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


  The default AWS OpsWorks Stacks agent version. You have the following options:

   

   
  * ``INHERIT`` - Use the stack's default agent version setting. 
   
  * *version_number* - Use the specified agent version. This value overrides the stack's default setting. To update the agent version, you must edit the instance configuration and specify a new version. AWS OpsWorks Stacks then automatically installs that version on the instance. 
   

   

  The default setting is ``INHERIT`` . To specify an agent version, you must use the complete version number, not the abbreviated number shown on the console. For a list of available agent version numbers, call  describe-agent-versions .

   

  AgentVersion cannot be set to Chef 12.2.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To update an instance**

The following example updates a specified instance's type. ::

  aws opsworks --region us-east-1 update-instance --instance-id dfe18b02-5327-493d-91a4-c5c0c448927f --instance-type c3.xlarge

*Output*: None.

**More Information**

For more information, see `Editing the Instance Configuration`_ in the *AWS OpsWorks User Guide*.

.. _`Editing the Instance Configuration`: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-properties.html



======
Output
======

None