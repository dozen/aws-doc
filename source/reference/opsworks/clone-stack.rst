[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks clone-stack:


***********
clone-stack
***********



===========
Description
===========



Creates a clone of a specified stack. For more information, see `Clone a Stack <http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-cloning.html>`_ . By default, all parameters are set to the values used by the parent stack.

 

 **Required Permissions** : To use this action, an IAM user must have an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/CloneStack>`_


========
Synopsis
========

::

    clone-stack
  --source-stack-id <value>
  [--name <value>]
  [--vpc-id <value>]
  [--attributes <value>]
  --service-role-arn <value>
  [--default-instance-profile-arn <value>]
  [--default-os <value>]
  [--hostname-theme <value>]
  [--default-availability-zone <value>]
  [--default-subnet-id <value>]
  [--custom-json <value>]
  [--configuration-manager <value>]
  [--chef-configuration <value>]
  [--use-custom-cookbooks | --no-use-custom-cookbooks]
  [--use-opsworks-security-groups | --no-use-opsworks-security-groups]
  [--custom-cookbooks-source <value>]
  [--default-ssh-key-name <value>]
  [--clone-permissions | --no-clone-permissions]
  [--clone-app-ids <value>]
  [--default-root-device-type <value>]
  [--agent-version <value>]
  [--stack-region <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--source-stack-id`` (string)


  The source stack ID.

  

``--name`` (string)


  The cloned stack name.

  

``--vpc-id`` (string)


  The ID of the VPC that the cloned stack is to be launched into. It must be in the specified region. All instances are launched into this VPC, and you cannot change the ID later.

   

   
  * If your account supports EC2 Classic, the default value is no VPC. 
   
  * If your account does not support EC2 Classic, the default value is the default VPC for the specified region. 
   

   

  If the VPC ID corresponds to a default VPC and you have specified either the ``DefaultAvailabilityZone`` or the ``DefaultSubnetId`` parameter only, AWS OpsWorks Stacks infers the value of the other parameter. If you specify neither parameter, AWS OpsWorks Stacks sets these parameters to the first valid Availability Zone for the specified region and the corresponding default VPC subnet ID, respectively. 

   

  If you specify a nondefault VPC ID, note the following:

   

   
  * It must belong to a VPC in your account that is in the specified region. 
   
  * You must specify a value for ``DefaultSubnetId`` . 
   

   

  For more information on how to use AWS OpsWorks Stacks with a VPC, see `Running a Stack in a VPC <http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-vpc.html>`_ . For more information on default VPC and EC2 Classic, see `Supported Platforms <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-supported-platforms.html>`_ . 

  

``--attributes`` (map)


  A list of stack attributes and values as key/value pairs to be added to the cloned stack.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string
  
  Where valid key names are:
    Color




JSON Syntax::

  {"Color": "string"
    ...}



``--service-role-arn`` (string)


  The stack AWS Identity and Access Management (IAM) role, which allows AWS OpsWorks Stacks to work with AWS resources on your behalf. You must set this parameter to the Amazon Resource Name (ARN) for an existing IAM role. If you create a stack by using the AWS OpsWorks Stacks console, it creates the role for you. You can obtain an existing stack's IAM ARN programmatically by calling  describe-permissions . For more information about IAM ARNs, see `Using Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ .

   

  .. note::

     

    You must set this parameter to a valid service role ARN or the action will fail; there is no default value. You can specify the source stack's service role ARN, if you prefer, but you must do so explicitly.

     

  

``--default-instance-profile-arn`` (string)


  The Amazon Resource Name (ARN) of an IAM profile that is the default profile for all of the stack's EC2 instances. For more information about IAM ARNs, see `Using Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ .

  

``--default-os`` (string)


  The stack's operating system, which must be set to one of the following.

   

   
  * A supported Linux operating system: An Amazon Linux version, such as ``Amazon Linux 2017.03`` , ``Amazon Linux 2016.09`` , ``Amazon Linux 2016.03`` , ``Amazon Linux 2015.09`` , or ``Amazon Linux 2015.03`` . 
   
  * A supported Ubuntu operating system, such as ``Ubuntu 16.04 LTS`` , ``Ubuntu 14.04 LTS`` , or ``Ubuntu 12.04 LTS`` . 
   
  * ``CentOS Linux 7``   
   
  * ``Red Hat Enterprise Linux 7``   
   
  * ``Microsoft Windows Server 2012 R2 Base`` , ``Microsoft Windows Server 2012 R2 with SQL Server Express`` , ``Microsoft Windows Server 2012 R2 with SQL Server Standard`` , or ``Microsoft Windows Server 2012 R2 with SQL Server Web`` . 
   
  * A custom AMI: ``Custom`` . You specify the custom AMI you want to use when you create instances. For more information on how to use custom AMIs with OpsWorks, see `Using Custom AMIs <http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-custom-ami.html>`_ . 
   

   

  The default option is the parent stack's operating system. For more information on the supported operating systems, see `AWS OpsWorks Stacks Operating Systems <http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-os.html>`_ .

   

  .. note::

     

    You can specify a different Linux operating system for the cloned stack, but you cannot change from Linux to Windows or Windows to Linux.

     

  

``--hostname-theme`` (string)


  The stack's host name theme, with spaces are replaced by underscores. The theme is used to generate host names for the stack's instances. By default, ``HostnameTheme`` is set to ``Layer_Dependent`` , which creates host names by appending integers to the layer's short name. The other themes are:

   

   
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


  The cloned stack's default Availability Zone, which must be in the specified region. For more information, see `Regions and Endpoints <http://docs.aws.amazon.com/general/latest/gr/rande.html>`_ . If you also specify a value for ``DefaultSubnetId`` , the subnet must be in the same zone. For more information, see the ``VpcId`` parameter description. 

  

``--default-subnet-id`` (string)


  The stack's default VPC subnet ID. This parameter is required if you specify a value for the ``VpcId`` parameter. All instances are launched into this subnet unless you specify otherwise when you create the instance. If you also specify a value for ``DefaultAvailabilityZone`` , the subnet must be in that zone. For information on default values and when this parameter is required, see the ``VpcId`` parameter description. 

  

``--custom-json`` (string)


  A string that contains user-defined, custom JSON. It is used to override the corresponding default stack configuration JSON values. The string should be in the following format:

   

   ``"{\"key1\": \"value1\", \"key2\": \"value2\",...}"``  

   

  For more information on custom JSON, see `Use Custom JSON to Modify the Stack Configuration Attributes <http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-json.html>`_  

  

``--configuration-manager`` (structure)


  The configuration manager. When you clone a stack we recommend that you use the configuration manager to specify the Chef version: 12, 11.10, or 11.4 for Linux stacks, or 12.2 for Windows stacks. The default value for Linux stacks is currently 12.

  



Shorthand Syntax::

    Name=string,Version=string




JSON Syntax::

  {
    "Name": "string",
    "Version": "string"
  }



``--chef-configuration`` (structure)


  A ``chef-configuration`` object that specifies whether to enable Berkshelf and the Berkshelf version on Chef 11.10 stacks. For more information, see `Create a New Stack <http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-creating.html>`_ .

  



Shorthand Syntax::

    ManageBerkshelf=boolean,BerkshelfVersion=string




JSON Syntax::

  {
    "ManageBerkshelf": true|false,
    "BerkshelfVersion": "string"
  }



``--use-custom-cookbooks`` | ``--no-use-custom-cookbooks`` (boolean)


  Whether to use custom cookbooks.

  

``--use-opsworks-security-groups`` | ``--no-use-opsworks-security-groups`` (boolean)


  Whether to associate the AWS OpsWorks Stacks built-in security groups with the stack's layers.

   

  AWS OpsWorks Stacks provides a standard set of built-in security groups, one for each layer, which are associated with layers by default. With ``UseOpsworksSecurityGroups`` you can instead provide your own custom security groups. ``UseOpsworksSecurityGroups`` has the following settings: 

   

   
  * True - AWS OpsWorks Stacks automatically associates the appropriate built-in security group with each layer (default setting). You can associate additional security groups with a layer after you create it but you cannot delete the built-in security group. 
   
  * False - AWS OpsWorks Stacks does not associate built-in security groups with layers. You must create appropriate Amazon Elastic Compute Cloud (Amazon EC2) security groups and associate a security group with each layer that you create. However, you can still manually associate a built-in security group with a layer on creation; custom security groups are required only for those layers that need custom settings. 
   

   

  For more information, see `Create a New Stack <http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-creating.html>`_ .

  

``--custom-cookbooks-source`` (structure)


  Contains the information required to retrieve an app or cookbook from a repository. For more information, see `Creating Apps <http://docs.aws.amazon.com/opsworks/latest/userguide/workingapps-creating.html>`_ or `Custom Recipes and Cookbooks <http://docs.aws.amazon.com/opsworks/latest/userguide/workingcookbook.html>`_ .

  



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


  A default Amazon EC2 key pair name. The default value is none. If you specify a key pair name, AWS OpsWorks installs the public key on the instance and you can use the private key with an SSH client to log in to the instance. For more information, see `Using SSH to Communicate with an Instance <http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-ssh.html>`_ and `Managing SSH Access <http://docs.aws.amazon.com/opsworks/latest/userguide/security-ssh-access.html>`_ . You can override this setting by specifying a different key pair, or no key pair, when you `create an instance <http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-add.html>`_ . 

  

``--clone-permissions`` | ``--no-clone-permissions`` (boolean)


  Whether to clone the source stack's permissions.

  

``--clone-app-ids`` (list)


  A list of source stack app IDs to be included in the cloned stack.

  



Syntax::

  "string" "string" ...



``--default-root-device-type`` (string)


  The default root device type. This value is used by default for all instances in the cloned stack, but you can override it when you create an instance. For more information, see `Storage for the Root Device <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ComponentsAMIs.html#storage-for-the-root-device>`_ .

  

  Possible values:

  
  *   ``ebs``

  
  *   ``instance-store``

  

  

``--agent-version`` (string)


  The default AWS OpsWorks Stacks agent version. You have the following options:

   

   
  * Auto-update - Set this parameter to ``LATEST`` . AWS OpsWorks Stacks automatically installs new agent versions on the stack's instances as soon as they are available. 
   
  * Fixed version - Set this parameter to your preferred agent version. To update the agent version, you must edit the stack configuration and specify a new version. AWS OpsWorks Stacks then automatically installs that version on the stack's instances. 
   

   

  The default setting is ``LATEST`` . To specify an agent version, you must use the complete version number, not the abbreviated number shown on the console. For a list of available agent version numbers, call  describe-agent-versions . AgentVersion cannot be set to Chef 12.2.

   

  .. note::

     

    You can also specify an agent version when you create or update an instance, which overrides the stack's default setting.

     

  

``--stack-region`` (string)


  The cloned stack AWS region, such as "ap-northeast-2". For more information about AWS regions, see `Regions and Endpoints <http://docs.aws.amazon.com/general/latest/gr/rande.html>`_ .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

StackId -> (string)

  

  The cloned stack ID.

  

  

