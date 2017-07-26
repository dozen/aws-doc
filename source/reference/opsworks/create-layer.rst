[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks create-layer:


************
create-layer
************



===========
Description
===========



Creates a layer. For more information, see `How to Create a Layer <http://docs.aws.amazon.com/opsworks/latest/userguide/workinglayers-basics-create.html>`_ .

 

.. note::

   

  You should use **create-layer** for noncustom layer types such as PHP App Server only if the stack does not have an existing layer of that type. A stack can have at most one instance of each noncustom layer; if you attempt to create a second instance, **create-layer** fails. A stack can have an arbitrary number of custom layers, so you can call **create-layer** as many times as you like for that layer type.

   

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/CreateLayer>`_


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
  [--cloud-watch-logs-configuration <value>]
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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-id`` (string)


  The layer stack ID.

  

``--type`` (string)


  The layer type. A stack cannot have more than one built-in layer of the same type. It can have any number of custom layers. Built-in layers are not available in Chef 12 stacks.

  

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


  For custom layers only, use this parameter to specify the layer's short name, which is used internally by AWS OpsWorks Stacks and by Chef recipes. The short name is also used as the name for the directory where your app files are installed. It can have a maximum of 200 characters, which are limited to the alphanumeric characters, '-', '_', and '.'.

   

  The built-in layers' short names are defined by AWS OpsWorks Stacks. For more information, see the `Layer Reference <http://docs.aws.amazon.com/opsworks/latest/userguide/layers.html>`_ .

  

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



``--cloud-watch-logs-configuration`` (structure)


  Specifies CloudWatch Logs configuration options for the layer. For more information, see  CloudWatchLogsLogStream .

  



Shorthand Syntax::

    Enabled=boolean,LogStreams=[{LogGroupName=string,DatetimeFormat=string,TimeZone=string,File=string,FileFingerprintLines=string,MultiLineStartPattern=string,InitialPosition=string,Encoding=string,BufferDuration=integer,BatchCount=integer,BatchSize=integer},{LogGroupName=string,DatetimeFormat=string,TimeZone=string,File=string,FileFingerprintLines=string,MultiLineStartPattern=string,InitialPosition=string,Encoding=string,BufferDuration=integer,BatchCount=integer,BatchSize=integer}]




JSON Syntax::

  {
    "Enabled": true|false,
    "LogStreams": [
      {
        "LogGroupName": "string",
        "DatetimeFormat": "string",
        "TimeZone": "LOCAL"|"UTC",
        "File": "string",
        "FileFingerprintLines": "string",
        "MultiLineStartPattern": "string",
        "InitialPosition": "start_of_file"|"end_of_file",
        "Encoding": "ascii"|"big5"|"big5hkscs"|"cp037"|"cp424"|"cp437"|"cp500"|"cp720"|"cp737"|"cp775"|"cp850"|"cp852"|"cp855"|"cp856"|"cp857"|"cp858"|"cp860"|"cp861"|"cp862"|"cp863"|"cp864"|"cp865"|"cp866"|"cp869"|"cp874"|"cp875"|"cp932"|"cp949"|"cp950"|"cp1006"|"cp1026"|"cp1140"|"cp1250"|"cp1251"|"cp1252"|"cp1253"|"cp1254"|"cp1255"|"cp1256"|"cp1257"|"cp1258"|"euc_jp"|"euc_jis_2004"|"euc_jisx0213"|"euc_kr"|"gb2312"|"gbk"|"gb18030"|"hz"|"iso2022_jp"|"iso2022_jp_1"|"iso2022_jp_2"|"iso2022_jp_2004"|"iso2022_jp_3"|"iso2022_jp_ext"|"iso2022_kr"|"latin_1"|"iso8859_2"|"iso8859_3"|"iso8859_4"|"iso8859_5"|"iso8859_6"|"iso8859_7"|"iso8859_8"|"iso8859_9"|"iso8859_10"|"iso8859_13"|"iso8859_14"|"iso8859_15"|"iso8859_16"|"johab"|"koi8_r"|"koi8_u"|"mac_cyrillic"|"mac_greek"|"mac_iceland"|"mac_latin2"|"mac_roman"|"mac_turkish"|"ptcp154"|"shift_jis"|"shift_jis_2004"|"shift_jisx0213"|"utf_32"|"utf_32_be"|"utf_32_le"|"utf_16"|"utf_16_be"|"utf_16_le"|"utf_7"|"utf_8"|"utf_8_sig",
        "BufferDuration": integer,
        "BatchCount": integer,
        "BatchSize": integer
      }
      ...
    ]
  }



``--custom-instance-profile-arn`` (string)


  The ARN of an IAM profile to be used for the layer's EC2 instances. For more information about IAM ARNs, see `Using Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ .

  

``--custom-json`` (string)


  A JSON-formatted string containing custom stack configuration and deployment attributes to be installed on the layer's instances. For more information, see `Using Custom JSON <http://docs.aws.amazon.com/opsworks/latest/userguide/workingcookbook-json-override.html>`_ . This feature is supported as of version 1.7.42 of the AWS CLI. 

  

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


  Whether to automatically assign an `Elastic IP address <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html>`_ to the layer's instances. For more information, see `How to Edit a Layer <http://docs.aws.amazon.com/opsworks/latest/userguide/workinglayers-basics-edit.html>`_ .

  

``--auto-assign-public-ips`` | ``--no-auto-assign-public-ips`` (boolean)


  For stacks that are running in a VPC, whether to automatically assign a public IP address to the layer's instances. For more information, see `How to Edit a Layer <http://docs.aws.amazon.com/opsworks/latest/userguide/workinglayers-basics-edit.html>`_ .

  

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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a layer**

The following ``create-layer`` command creates a PHP App Server layer named MyPHPLayer in a specified stack. ::

  aws opsworks create-layer --region us-east-1 --stack-id f6673d70-32e6-4425-8999-265dd002fec7 --type php-app --name MyPHPLayer --shortname myphplayer

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

  

  

