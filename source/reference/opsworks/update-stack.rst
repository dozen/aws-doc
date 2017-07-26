[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks update-stack:


************
update-stack
************



===========
Description
===========



Updates a specified stack.

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    update-stack
  --stack-id <value>
  [--name <value>]
  [--attributes <value>]
  [--service-role-arn <value>]
  [--default-instance-profile-arn <value>]
  [--default-os <value>]
  [--hostname-theme <value>]
  [--default-availability-zone <value>]
  [--default-subnet-id <value>]
  [--custom-json <value>]
  [--configuration-manager <value>]
  [--chef-configuration <value>]
  [--use-custom-cookbooks | --no-use-custom-cookbooks]
  [--custom-cookbooks-source <value>]
  [--default-ssh-key-name <value>]
  [--default-root-device-type <value>]
  [--use-opsworks-security-groups | --no-use-opsworks-security-groups]
  [--agent-version <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-id`` (string)


  The stack ID.

  

``--name`` (string)


  The stack's new name.

  

``--attributes`` (map)


  One or more user-defined key-value pairs to be added to the stack attributes.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string
  
  Where valid key names are:
    Color




JSON Syntax::

  {"Color": "string"
    ...}



``--service-role-arn`` (string)


  Do not use this parameter. You cannot update a stack's service role.

  

``--default-instance-profile-arn`` (string)


  The ARN of an IAM profile that is the default profile for all of the stack's EC2 instances. For more information about IAM ARNs, see `Using Identifiers`_ .

  

``--default-os`` (string)


  The stack's operating system, which must be set to one of the following:

   

   
  * A supported Linux operating system: An Amazon Linux version, such as ``Amazon Linux 2015.03`` , ``Red Hat Enterprise Linux 7`` , ``Ubuntu 12.04 LTS`` , or ``Ubuntu 14.04 LTS`` .
   
  * ``Microsoft Windows Server 2012 R2 Base`` .
   
  * A custom AMI: ``Custom`` . You specify the custom AMI you want to use when you create instances. For more information on how to use custom AMIs with OpsWorks, see `Using Custom AMIs`_ .
   

   

  The default option is the stack's current operating system. For more information on the supported operating systems, see `AWS OpsWorks Operating Systems`_ .

  

``--hostname-theme`` (string)


  The stack's new host name theme, with spaces replaced by underscores. The theme is used to generate host names for the stack's instances. By default, ``HostnameTheme`` is set to ``Layer_Dependent`` , which creates host names by appending integers to the layer's short name. The other themes are:

   

   
  * ``Baked_Goods``  
   
  * ``Clouds``  
   
  * ``Europe_Cities``  
   
  * ``Fruits``  
   
  * ``Greek_Deities``  
   
  * ``Legendary_creatures_from_Japan``  
   
  * ``Planets_and_Moons``  
   
  * ``Roman_Deities``  
   
  * ``Scottish_Islands``  
   
  * ``US_Cities``  
   
  * ``Wild_Cats``  
   

   

  To obtain a generated host name, call ``GetHostNameSuggestion`` , which returns a host name based on the current theme.

  

``--default-availability-zone`` (string)


  The stack's default Availability Zone, which must be in the stack's region. For more information, see `Regions and Endpoints`_ . If you also specify a value for ``DefaultSubnetId`` , the subnet must be in the same zone. For more information, see  create-stack . 

  

``--default-subnet-id`` (string)


  The stack's default VPC subnet ID. This parameter is required if you specify a value for the ``VpcId`` parameter. All instances are launched into this subnet unless you specify otherwise when you create the instance. If you also specify a value for ``DefaultAvailabilityZone`` , the subnet must be in that zone. For information on default values and when this parameter is required, see the ``VpcId`` parameter description. 

  

``--custom-json`` (string)


  A string that contains user-defined, custom JSON. It can be used to override the corresponding default stack configuration JSON values or to pass data to recipes. The string should be in the following format and escape characters such as '"':

   

   ``"{\"key1\": \"value1\", \"key2\": \"value2\",...}"``  

   

  For more information on custom JSON, see `Use Custom JSON to Modify the Stack Configuration Attributes`_ .

  

``--configuration-manager`` (structure)


  The configuration manager. When you update a stack, we recommend that you use the configuration manager to specify the Chef version: 12, 11.10, or 11.4 for Linux stacks, or 12.2 for Windows stacks. The default value for Linux stacks is currently 11.4.

  



Shorthand Syntax::

    Name=string,Version=string




JSON Syntax::

  {
    "Name": "string",
    "Version": "string"
  }



``--chef-configuration`` (structure)


  A ``chef-configuration`` object that specifies whether to enable Berkshelf and the Berkshelf version on Chef 11.10 stacks. For more information, see `Create a New Stack`_ .

  



Shorthand Syntax::

    ManageBerkshelf=boolean,BerkshelfVersion=string




JSON Syntax::

  {
    "ManageBerkshelf": true|false,
    "BerkshelfVersion": "string"
  }



``--use-custom-cookbooks`` | ``--no-use-custom-cookbooks`` (boolean)


  Whether the stack uses custom cookbooks.

  

``--custom-cookbooks-source`` (structure)


  Contains the information required to retrieve an app or cookbook from a repository. For more information, see `Creating Apps`_ or `Custom Recipes and Cookbooks`_ .

  



Shorthand Syntax::

    Type=string,Url=string,Username=string,Password=string,SshKey=string,Revision=string




JSON Syntax::

  {
    "Type": "git"|"svn"|"archive"|"s3",
    "Url": "string",
    "Username": "string",
    "Password": "string",
    "SshKey": "string",
    "Revision": "string"
  }



``--default-ssh-key-name`` (string)


  A default Amazon EC2 key-pair name. The default value is ``none`` . If you specify a key-pair name, AWS OpsWorks installs the public key on the instance and you can use the private key with an SSH client to log in to the instance. For more information, see `Using SSH to Communicate with an Instance`_ and `Managing SSH Access`_ . You can override this setting by specifying a different key pair, or no key pair, when you `create an instance`_ . 

  

``--default-root-device-type`` (string)


  The default root device type. This value is used by default for all instances in the stack, but you can override it when you create an instance. For more information, see `Storage for the Root Device`_ .

  

  Possible values:

  
  *   ``ebs``

  
  *   ``instance-store``

  

  

``--use-opsworks-security-groups`` | ``--no-use-opsworks-security-groups`` (boolean)


  Whether to associate the AWS OpsWorks built-in security groups with the stack's layers.

   

  AWS OpsWorks provides a standard set of built-in security groups, one for each layer, which are associated with layers by default. ``UseOpsworksSecurityGroups`` allows you to provide your own custom security groups instead of using the built-in groups. ``UseOpsworksSecurityGroups`` has the following settings: 

   

   
  * True - AWS OpsWorks automatically associates the appropriate built-in security group with each layer (default setting). You can associate additional security groups with a layer after you create it, but you cannot delete the built-in security group. 
   
  * False - AWS OpsWorks does not associate built-in security groups with layers. You must create appropriate EC2 security groups and associate a security group with each layer that you create. However, you can still manually associate a built-in security group with a layer on. Custom security groups are required only for those layers that need custom settings. 
   

   

  For more information, see `Create a New Stack`_ .

  

``--agent-version`` (string)


  The default AWS OpsWorks agent version. You have the following options:

   

   
  * Auto-update - Set this parameter to ``LATEST`` . AWS OpsWorks automatically installs new agent versions on the stack's instances as soon as they are available.
   
  * Fixed version - Set this parameter to your preferred agent version. To update the agent version, you must edit the stack configuration and specify a new version. AWS OpsWorks then automatically installs that version on the stack's instances.
   

   

  The default setting is ``LATEST`` . To specify an agent version, you must use the complete version number, not the abbreviated number shown on the console. For a list of available agent version numbers, call  describe-agent-versions .

   

  .. note::

    You can also specify an agent version when you create or update an instance, which overrides the stack's default setting.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Creating Apps: http://docs.aws.amazon.com/opsworks/latest/userguide/workingapps-creating.html
.. _Managing SSH Access: http://docs.aws.amazon.com/opsworks/latest/userguide/security-ssh-access.html
.. _Using SSH to Communicate with an Instance: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-ssh.html
.. _Storage for the Root Device: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ComponentsAMIs.html#storage-for-the-root-device
.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
.. _Use Custom JSON to Modify the Stack Configuration Attributes: http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-json.html
.. _Using Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _Custom Recipes and Cookbooks: http://docs.aws.amazon.com/opsworks/latest/userguide/workingcookbook.html
.. _Regions and Endpoints: http://docs.aws.amazon.com/general/latest/gr/rande.html
.. _Create a New Stack: http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-creating.html
.. _AWS OpsWorks Operating Systems: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-os.html
.. _create an instance: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-add.html
.. _Using Custom AMIs: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-custom-ami.html
