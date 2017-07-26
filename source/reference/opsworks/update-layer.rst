[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks update-layer:


************
update-layer
************



===========
Description
===========



Updates a specified layer.

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    update-layer
  --layer-id <value>
  [--name <value>]
  [--shortname <value>]
  [--attributes <value>]
  [--custom-instance-profile-arn <value>]
  [--custom-json <value>]
  [--custom-security-group-ids <value>]
  [--packages <value>]
  [--volume-configurations <value>]
  [--enable-auto-healing | --no-enable-auto-healing]
  [--auto-assign-elastic-ips | --no-auto-assign-elastic-ips]
  [--auto-assign-public-ips | --no-auto-assign-public-ips]
  [--custom-recipes <value>]
  [--install-updates-on-boot | --no-install-updates-on-boot]
  [--use-ebs-optimized-instances | --no-use-ebs-optimized-instances]
  [--lifecycle-event-configuration <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--layer-id`` (string)


  The layer ID.

  

``--name`` (string)


  The layer name, which is used by the console.

  

``--shortname`` (string)


  For custom layers only, use this parameter to specify the layer's short name, which is used internally by AWS OpsWorksand by Chef. The short name is also used as the name for the directory where your app files are installed. It can have a maximum of 200 characters and must be in the following format: /\A[a-z0-9\-\_\.]+\Z/.

   

  The built-in layers' short names are defined by AWS OpsWorks. For more information, see the `Layer Reference`_ 

  

``--attributes`` (map)


  One or more user-defined key/value pairs to be added to the stack attributes.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string
  
  Where valid key names are:
    EcsClusterArn
    EnableHaproxyStats
    HaproxyStatsUrl
    HaproxyStatsUser
    HaproxyStatsPassword
    HaproxyHealthCheckUrl
    HaproxyHealthCheckMethod
    MysqlRootPassword
    MysqlRootPasswordUbiquitous
    GangliaUrl
    GangliaUser
    GangliaPassword
    MemcachedMemory
    NodejsVersion
    RubyVersion
    RubygemsVersion
    ManageBundler
    BundlerVersion
    RailsStack
    PassengerVersion
    Jvm
    JvmVersion
    JvmOptions
    JavaAppServer
    JavaAppServerVersion




JSON Syntax::

  {"EcsClusterArn"|"EnableHaproxyStats"|"HaproxyStatsUrl"|"HaproxyStatsUser"|"HaproxyStatsPassword"|"HaproxyHealthCheckUrl"|"HaproxyHealthCheckMethod"|"MysqlRootPassword"|"MysqlRootPasswordUbiquitous"|"GangliaUrl"|"GangliaUser"|"GangliaPassword"|"MemcachedMemory"|"NodejsVersion"|"RubyVersion"|"RubygemsVersion"|"ManageBundler"|"BundlerVersion"|"RailsStack"|"PassengerVersion"|"Jvm"|"JvmVersion"|"JvmOptions"|"JavaAppServer"|"JavaAppServerVersion": "string"
    ...}



``--custom-instance-profile-arn`` (string)


  The ARN of an IAM profile to be used for all of the layer's EC2 instances. For more information about IAM ARNs, see `Using Identifiers`_ .

  

``--custom-json`` (string)


  A JSON-formatted string containing custom stack configuration and deployment attributes to be installed on the layer's instances. For more information, see `Using Custom JSON`_ . 

  

``--custom-security-group-ids`` (list)


  An array containing the layer's custom security group IDs.

  



Syntax::

  "string" "string" ...



``--packages`` (list)


  An array of ``Package`` objects that describe the layer's packages.

  



Syntax::

  "string" "string" ...



``--volume-configurations`` (list)


  A ``volume-configurations`` object that describes the layer's Amazon EBS volumes.

  



Shorthand Syntax::

    MountPoint=string,RaidLevel=integer,NumberOfDisks=integer,Size=integer,VolumeType=string,Iops=integer ...




JSON Syntax::

  [
    {
      "MountPoint": "string",
      "RaidLevel": integer,
      "NumberOfDisks": integer,
      "Size": integer,
      "VolumeType": "string",
      "Iops": integer
    }
    ...
  ]



``--enable-auto-healing`` | ``--no-enable-auto-healing`` (boolean)


  Whether to disable auto healing for the layer.

  

``--auto-assign-elastic-ips`` | ``--no-auto-assign-elastic-ips`` (boolean)


  Whether to automatically assign an `Elastic IP address`_ to the layer's instances. For more information, see `How to Edit a Layer`_ .

  

``--auto-assign-public-ips`` | ``--no-auto-assign-public-ips`` (boolean)


  For stacks that are running in a VPC, whether to automatically assign a public IP address to the layer's instances. For more information, see `How to Edit a Layer`_ .

  

``--custom-recipes`` (structure)


  A ``LayerCustomRecipes`` object that specifies the layer's custom recipes.

  



Shorthand Syntax::

    Setup=string,string,Configure=string,string,Deploy=string,string,Undeploy=string,string,Shutdown=string,string




JSON Syntax::

  {
    "Setup": ["string", ...],
    "Configure": ["string", ...],
    "Deploy": ["string", ...],
    "Undeploy": ["string", ...],
    "Shutdown": ["string", ...]
  }



``--install-updates-on-boot`` | ``--no-install-updates-on-boot`` (boolean)


  Whether to install operating system and package updates when the instance boots. The default value is ``true`` . To control when updates are installed, set this value to ``false`` . You must then update your instances manually by using  create-deployment to run the ``update_dependencies`` stack command or manually running ``yum`` (Amazon Linux) or ``apt-get`` (Ubuntu) on the instances. 

   

  .. note::

     

    We strongly recommend using the default value of ``true`` , to ensure that your instances have the latest security updates.

     

  

``--use-ebs-optimized-instances`` | ``--no-use-ebs-optimized-instances`` (boolean)


  Whether to use Amazon EBS-optimized instances.

  

``--lifecycle-event-configuration`` (structure)


  

  



Shorthand Syntax::

    Shutdown={ExecutionTimeout=integer,DelayUntilElbConnectionsDrained=boolean}




JSON Syntax::

  {
    "Shutdown": {
      "ExecutionTimeout": integer,
      "DelayUntilElbConnectionsDrained": true|false
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To update a layer**

The following example updates a specified layer to use Amazon EBS-optimized instances. ::

  aws opsworks --region us-east-1 update-layer --layer-id 888c5645-09a5-4d0e-95a8-812ef1db76a4 --use-ebs-optimized-instances

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: None.

**More Information**

For more information, see `Editing an OpsWorks Layer's Configuration`_ in the *AWS OpsWorks User Guide*.

.. _`Editing an OpsWorks Layer's Configuration`: http://docs.aws.amazon.com/opsworks/latest/userguide/workinglayers-basics-edit.html



======
Output
======

None

.. _Using Custom JSON: http://docs.aws.amazon.com/opsworks/latest/userguide/workingcookbook-json-override.html
.. _Layer Reference: http://docs.aws.amazon.com/opsworks/latest/userguide/layers.html
.. _Using Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _Elastic IP address: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html
.. _How to Edit a Layer: http://docs.aws.amazon.com/opsworks/latest/userguide/workinglayers-basics-edit.html
.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
