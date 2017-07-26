[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks create-layer:


************
create-layer
************



===========
Description
===========



Creates a layer. For more information, see `How to Create a Layer`_ .

 

.. note::

   

  You should use **create-layer** for noncustom layer types such as PHP App Server only if the stack does not have an existing layer of that type. A stack can have at most one instance of each noncustom layer; if you attempt to create a second instance, **create-layer** fails. A stack can have an arbitrary number of custom layers, so you can call **create-layer** as many times as you like for that layer type.

   

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    create-layer
  --stack-id <value>
  --type <value>
  --name <value>
  --shortname <value>
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

``--stack-id`` (string)


  The layer stack ID.

  

``--type`` (string)


  The layer type. A stack cannot have more than one built-in layer of the same type. It can have any number of custom layers.

  

  Possible values:

  
  *   ``aws-flow-ruby``

  
  *   ``ecs-cluster``

  
  *   ``java-app``

  
  *   ``lb``

  
  *   ``web``

  
  *   ``php-app``

  
  *   ``rails-app``

  
  *   ``nodejs-app``

  
  *   ``memcached``

  
  *   ``db-master``

  
  *   ``monitoring-master``

  
  *   ``custom``

  

  

``--name`` (string)


  The layer name, which is used by the console.

  

``--shortname`` (string)


  For custom layers only, use this parameter to specify the layer's short name, which is used internally by AWS OpsWorks and by Chef recipes. The short name is also used as the name for the directory where your app files are installed. It can have a maximum of 200 characters, which are limited to the alphanumeric characters, '-', '_', and '.'.

   

  The built-in layers' short names are defined by AWS OpsWorks. For more information, see the `Layer Reference`_ .

  

``--attributes`` (map)


  One or more user-defined key-value pairs to be added to the stack attributes.

   

  To create a cluster layer, set the ``EcsClusterArn`` attribute to the cluster's ARN.

  



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


  The ARN of an IAM profile to be used for the layer's EC2 instances. For more information about IAM ARNs, see `Using Identifiers`_ .

  

``--custom-json`` (string)


  A JSON-formatted string containing custom stack configuration and deployment attributes to be installed on the layer's instances. For more information, see `Using Custom JSON`_ . This feature is supported as of version 1.7.42 of the AWS CLI. 

  

``--custom-security-group-ids`` (list)


  An array containing the layer custom security group IDs.

  



Syntax::

  "string" "string" ...



``--packages`` (list)


  An array of ``Package`` objects that describes the layer packages.

  



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


  A ``LayerCustomRecipes`` object that specifies the layer custom recipes.

  



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


  Whether to install operating system and package updates when the instance boots. The default value is ``true`` . To control when updates are installed, set this value to ``false`` . You must then update your instances manually by using  create-deployment to run the ``update_dependencies`` stack command or by manually running ``yum`` (Amazon Linux) or ``apt-get`` (Ubuntu) on the instances. 

   

  .. note::

     

    To ensure that your instances have the latest security updates, we strongly recommend using the default value of ``true`` .

     

  

``--use-ebs-optimized-instances`` | ``--no-use-ebs-optimized-instances`` (boolean)


  Whether to use Amazon EBS-optimized instances.

  

``--lifecycle-event-configuration`` (structure)


  A ``LifeCycleEventConfiguration`` object that you can use to configure the Shutdown event to specify an execution timeout and enable or disable Elastic Load Balancer connection draining.

  



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

**To create a layer**

The following ``create-layer`` command creates a PHP App Server layer named MyPHPLayer in a specified stack. ::

  aws opsworks create-layer --region us-east-1 --stack-id f6673d70-32e6-4425-8999-265dd002fec7 --type php-app --name MyPHPLayer --shortname myphplayer

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*::

  {
    "LayerId": "0b212672-6b4b-40e4-8a34-5a943cf2e07a"
  }

**More Information**

For more information, see `How to Create a Layer`_ in the *AWS OpsWorks User Guide*.

.. _`How to Create a Layer`: http://docs.aws.amazon.com/opsworks/latest/userguide/workinglayers-basics-create.html


======
Output
======

LayerId -> (string)

  

  The layer ID.

  

  



.. _Using Custom JSON: http://docs.aws.amazon.com/opsworks/latest/userguide/workingcookbook-json-override.html
.. _Layer Reference: http://docs.aws.amazon.com/opsworks/latest/userguide/layers.html
.. _How to Create a Layer: http://docs.aws.amazon.com/opsworks/latest/userguide/workinglayers-basics-create.html
.. _Using Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _Elastic IP address: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html
.. _How to Edit a Layer: http://docs.aws.amazon.com/opsworks/latest/userguide/workinglayers-basics-edit.html
.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
