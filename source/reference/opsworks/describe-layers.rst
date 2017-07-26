[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-layers:


***************
describe-layers
***************



===========
Description
===========



Requests a description of one or more layers in a specified stack.

 

.. note::

   

  This call accepts only one resource-identifying parameter.

   

 

 **Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DescribeLayers>`_


========
Synopsis
========

::

    describe-layers
  [--stack-id <value>]
  [--layer-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-id`` (string)


  The stack ID.

  

``--layer-ids`` (list)


  An array of layer IDs that specify the layers to be described. If you omit this parameter, ``describe-layers`` returns a description of every layer in the specified stack.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a stack's layers**

The following ``describe-layers`` commmand describes the layers in a specified stack::

  aws opsworks --region us-east-1 describe-layers --stack-id 38ee91e2-abdc-4208-a107-0b7168b3cc7a

*Output*::

  {
    "Layers": [
        {
            "StackId": "38ee91e2-abdc-4208-a107-0b7168b3cc7a",
            "Type": "db-master",
            "DefaultSecurityGroupNames": [
                "AWS-OpsWorks-DB-Master-Server"
            ],
            "Name": "MySQL",
            "Packages": [],
            "DefaultRecipes": {
                "Undeploy": [],
                "Setup": [
                    "opsworks_initial_setup",
                    "ssh_host_keys",
                    "ssh_users",
                    "mysql::client",
                    "dependencies",
                    "ebs",
                    "opsworks_ganglia::client",
                    "mysql::server",
                    "dependencies",
                    "deploy::mysql"
                ],
                "Configure": [
                    "opsworks_ganglia::configure-client",
                    "ssh_users",
                    "agent_version",
                    "deploy::mysql"
                ],
                "Shutdown": [
                    "opsworks_shutdown::default",
                    "mysql::stop"
                ],
                "Deploy": [
                    "deploy::default",
                    "deploy::mysql"
                ]
            },
            "CustomRecipes": {
                "Undeploy": [],
                "Setup": [],
                "Configure": [],
                "Shutdown": [],
                "Deploy": []
            },
            "EnableAutoHealing": false,
            "LayerId": "41a20847-d594-4325-8447-171821916b73",
            "Attributes": {
                "MysqlRootPasswordUbiquitous": "true",
                "RubygemsVersion": null,
                "RailsStack": null,
                "HaproxyHealthCheckMethod": null,
                "RubyVersion": null,
                "BundlerVersion": null,
                "HaproxyStatsPassword": null,
                "PassengerVersion": null,
                "MemcachedMemory": null,
                "EnableHaproxyStats": null,
                "ManageBundler": null,
                "NodejsVersion": null,
                "HaproxyHealthCheckUrl": null,
                "MysqlRootPassword": "*****FILTERED*****",
                "GangliaPassword": null,
                "GangliaUser": null,
                "HaproxyStatsUrl": null,
                "GangliaUrl": null,
                "HaproxyStatsUser": null
            },
            "Shortname": "db-master",
            "AutoAssignElasticIps": false,
            "CustomSecurityGroupIds": [],
            "CreatedAt": "2013-07-25T18:11:19+00:00",
            "VolumeConfigurations": [
                {
                    "MountPoint": "/vol/mysql",
                    "Size": 10,
                    "NumberOfDisks": 1
                }
            ]
        },
        {
            "StackId": "38ee91e2-abdc-4208-a107-0b7168b3cc7a",
            "Type": "custom",
            "DefaultSecurityGroupNames": [
                "AWS-OpsWorks-Custom-Server"
            ],
            "Name": "TomCustom",
            "Packages": [],
            "DefaultRecipes": {
                "Undeploy": [],
                "Setup": [
                    "opsworks_initial_setup",
                    "ssh_host_keys",
                    "ssh_users",
                    "mysql::client",
                    "dependencies",
                    "ebs",
                    "opsworks_ganglia::client"
                ],
                "Configure": [
                    "opsworks_ganglia::configure-client",
                    "ssh_users",
                    "agent_version"
                ],
                "Shutdown": [
                    "opsworks_shutdown::default"
                ],
                "Deploy": [
                    "deploy::default"
                ]
            },
            "CustomRecipes": {
                "Undeploy": [],
                "Setup": [
                    "tomcat::setup"
                ],
                "Configure": [
                    "tomcat::configure"
                ],
                "Shutdown": [],
                "Deploy": [
                    "tomcat::deploy"
                ]
            },
            "EnableAutoHealing": true,
            "LayerId": "e6cbcd29-d223-40fc-8243-2eb213377440",
            "Attributes": {
                "MysqlRootPasswordUbiquitous": null,
                "RubygemsVersion": null,
                "RailsStack": null,
                "HaproxyHealthCheckMethod": null,
                "RubyVersion": null,
                "BundlerVersion": null,
                "HaproxyStatsPassword": null,
                "PassengerVersion": null,
                "MemcachedMemory": null,
                "EnableHaproxyStats": null,
                "ManageBundler": null,
                "NodejsVersion": null,
                "HaproxyHealthCheckUrl": null,
                "MysqlRootPassword": null,
                "GangliaPassword": null,
                "GangliaUser": null,
                "HaproxyStatsUrl": null,
                "GangliaUrl": null,
                "HaproxyStatsUser": null
            },
            "Shortname": "tomcustom",
            "AutoAssignElasticIps": false,
            "CustomSecurityGroupIds": [],
            "CreatedAt": "2013-07-25T18:12:53+00:00",
            "VolumeConfigurations": []
        }
    ]
  }

**More Information**

For more information, see Layers_ in the *AWS OpsWorks User Guide*.

.. _Layers: http://docs.aws.amazon.com/opsworks/latest/userguide/workinglayers.html



======
Output
======

Layers -> (list)

  

  An array of ``Layer`` objects that describe the layers.

  

  (structure)

    

    Describes a layer.

    

    Arn -> (string)

      

      

    StackId -> (string)

      

      The layer stack ID.

      

      

    LayerId -> (string)

      

      The layer ID.

      

      

    Type -> (string)

      

      The layer type.

      

      

    Name -> (string)

      

      The layer name.

      

      

    Shortname -> (string)

      

      The layer short name.

      

      

    Attributes -> (map)

      

      The layer attributes.

       

      For the ``HaproxyStatsPassword`` , ``MysqlRootPassword`` , and ``GangliaPassword`` attributes, AWS OpsWorks Stacks returns ``*****FILTERED*****`` instead of the actual value

       

      For an ECS Cluster layer, AWS OpsWorks Stacks the ``EcsClusterArn`` attribute is set to the cluster's ARN.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    CloudWatchLogsConfiguration -> (structure)

      

      The Amazon CloudWatch Logs configuration settings for the layer.

      

      Enabled -> (boolean)

        

        Whether CloudWatch Logs is enabled for a layer.

        

        

      LogStreams -> (list)

        

        A list of configuration options for CloudWatch Logs.

        

        (structure)

          

          Describes the Amazon CloudWatch logs configuration for a layer. For detailed information about members of this data type, see the `CloudWatch Logs Agent Reference <http://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/AgentReference.html>`_ .

          

          LogGroupName -> (string)

            

            Specifies the destination log group. A log group is created automatically if it doesn't already exist. Log group names can be between 1 and 512 characters long. Allowed characters include a-z, A-Z, 0-9, '_' (underscore), '-' (hyphen), '/' (forward slash), and '.' (period).

            

            

          DatetimeFormat -> (string)

            

            Specifies how the time stamp is extracted from logs. For more information, see the `CloudWatch Logs Agent Reference <http://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/AgentReference.html>`_ .

            

            

          TimeZone -> (string)

            

            Specifies the time zone of log event time stamps.

            

            

          File -> (string)

            

            Specifies log files that you want to push to CloudWatch Logs.

             

             ``File`` can point to a specific file or multiple files (by using wild card characters such as ``/var/log/system.log*`` ). Only the latest file is pushed to CloudWatch Logs, based on file modification time. We recommend that you use wild card characters to specify a series of files of the same type, such as ``access_log.2014-06-01-01`` , ``access_log.2014-06-01-02`` , and so on by using a pattern like ``access_log.*`` . Don't use a wildcard to match multiple file types, such as ``access_log_80`` and ``access_log_443`` . To specify multiple, different file types, add another log stream entry to the configuration file, so that each log file type is stored in a different log group.

             

            Zipped files are not supported.

            

            

          FileFingerprintLines -> (string)

            

            Specifies the range of lines for identifying a file. The valid values are one number, or two dash-delimited numbers, such as '1', '2-5'. The default value is '1', meaning the first line is used to calculate the fingerprint. Fingerprint lines are not sent to CloudWatch Logs unless all specified lines are available.

            

            

          MultiLineStartPattern -> (string)

            

            Specifies the pattern for identifying the start of a log message.

            

            

          InitialPosition -> (string)

            

            Specifies where to start to read data (start_of_file or end_of_file). The default is start_of_file. This setting is only used if there is no state persisted for that log stream.

            

            

          Encoding -> (string)

            

            Specifies the encoding of the log file so that the file can be read correctly. The default is ``utf_8`` . Encodings supported by Python ``codecs.decode()`` can be used here.

            

            

          BufferDuration -> (integer)

            

            Specifies the time duration for the batching of log events. The minimum value is 5000ms and default value is 5000ms.

            

            

          BatchCount -> (integer)

            

            Specifies the max number of log events in a batch, up to 10000. The default value is 1000.

            

            

          BatchSize -> (integer)

            

            Specifies the maximum size of log events in a batch, in bytes, up to 1048576 bytes. The default value is 32768 bytes. This size is calculated as the sum of all event messages in UTF-8, plus 26 bytes for each log event.

            

            

          

        

      

    CustomInstanceProfileArn -> (string)

      

      The ARN of the default IAM profile to be used for the layer's EC2 instances. For more information about IAM ARNs, see `Using Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ .

      

      

    CustomJson -> (string)

      

      A JSON formatted string containing the layer's custom stack configuration and deployment attributes.

      

      

    CustomSecurityGroupIds -> (list)

      

      An array containing the layer's custom security group IDs.

      

      (string)

        

        

      

    DefaultSecurityGroupNames -> (list)

      

      An array containing the layer's security group names.

      

      (string)

        

        

      

    Packages -> (list)

      

      An array of ``Package`` objects that describe the layer's packages.

      

      (string)

        

        

      

    VolumeConfigurations -> (list)

      

      A ``VolumeConfigurations`` object that describes the layer's Amazon EBS volumes.

      

      (structure)

        

        Describes an Amazon EBS volume configuration.

        

        MountPoint -> (string)

          

          The volume mount point. For example "/dev/sdh".

          

          

        RaidLevel -> (integer)

          

          The volume `RAID level <http://en.wikipedia.org/wiki/Standard_RAID_levels>`_ .

          

          

        NumberOfDisks -> (integer)

          

          The number of disks in the volume.

          

          

        Size -> (integer)

          

          The volume size.

          

          

        VolumeType -> (string)

          

          The volume type:

           

           
          * ``standard`` - Magnetic 
           
          * ``io1`` - Provisioned IOPS (SSD) 
           
          * ``gp2`` - General Purpose (SSD) 
           

          

          

        Iops -> (integer)

          

          For PIOPS volumes, the IOPS per disk.

          

          

        

      

    EnableAutoHealing -> (boolean)

      

      Whether auto healing is disabled for the layer.

      

      

    AutoAssignElasticIps -> (boolean)

      

      Whether to automatically assign an `Elastic IP address <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html>`_ to the layer's instances. For more information, see `How to Edit a Layer <http://docs.aws.amazon.com/opsworks/latest/userguide/workinglayers-basics-edit.html>`_ .

      

      

    AutoAssignPublicIps -> (boolean)

      

      For stacks that are running in a VPC, whether to automatically assign a public IP address to the layer's instances. For more information, see `How to Edit a Layer <http://docs.aws.amazon.com/opsworks/latest/userguide/workinglayers-basics-edit.html>`_ .

      

      

    DefaultRecipes -> (structure)

      

      AWS OpsWorks Stacks supports five lifecycle events: **setup** , **configuration** , **deploy** , **undeploy** , and **shutdown** . For each layer, AWS OpsWorks Stacks runs a set of standard recipes for each event. In addition, you can provide custom recipes for any or all layers and events. AWS OpsWorks Stacks runs custom event recipes after the standard recipes. ``LayerCustomRecipes`` specifies the custom recipes for a particular layer to be run in response to each of the five events. 

       

      To specify a recipe, use the cookbook's directory name in the repository followed by two colons and the recipe name, which is the recipe's file name without the .rb extension. For example: phpapp2::dbsetup specifies the dbsetup.rb recipe in the repository's phpapp2 folder.

      

      Setup -> (list)

        

        An array of custom recipe names to be run following a ``setup`` event.

        

        (string)

          

          

        

      Configure -> (list)

        

        An array of custom recipe names to be run following a ``configure`` event.

        

        (string)

          

          

        

      Deploy -> (list)

        

        An array of custom recipe names to be run following a ``deploy`` event.

        

        (string)

          

          

        

      Undeploy -> (list)

        

        An array of custom recipe names to be run following a ``undeploy`` event.

        

        (string)

          

          

        

      Shutdown -> (list)

        

        An array of custom recipe names to be run following a ``shutdown`` event.

        

        (string)

          

          

        

      

    CustomRecipes -> (structure)

      

      A ``LayerCustomRecipes`` object that specifies the layer's custom recipes.

      

      Setup -> (list)

        

        An array of custom recipe names to be run following a ``setup`` event.

        

        (string)

          

          

        

      Configure -> (list)

        

        An array of custom recipe names to be run following a ``configure`` event.

        

        (string)

          

          

        

      Deploy -> (list)

        

        An array of custom recipe names to be run following a ``deploy`` event.

        

        (string)

          

          

        

      Undeploy -> (list)

        

        An array of custom recipe names to be run following a ``undeploy`` event.

        

        (string)

          

          

        

      Shutdown -> (list)

        

        An array of custom recipe names to be run following a ``shutdown`` event.

        

        (string)

          

          

        

      

    CreatedAt -> (string)

      

      Date when the layer was created.

      

      

    InstallUpdatesOnBoot -> (boolean)

      

      Whether to install operating system and package updates when the instance boots. The default value is ``true`` . If this value is set to ``false`` , you must then update your instances manually by using  create-deployment to run the ``update_dependencies`` stack command or manually running ``yum`` (Amazon Linux) or ``apt-get`` (Ubuntu) on the instances. 

       

      .. note::

         

        We strongly recommend using the default value of ``true`` , to ensure that your instances have the latest security updates.

         

      

      

    UseEbsOptimizedInstances -> (boolean)

      

      Whether the layer uses Amazon EBS-optimized instances.

      

      

    LifecycleEventConfiguration -> (structure)

      

      A ``LifeCycleEventConfiguration`` object that specifies the Shutdown event configuration.

      

      Shutdown -> (structure)

        

        A ``ShutdownEventConfiguration`` object that specifies the Shutdown event configuration.

        

        ExecutionTimeout -> (integer)

          

          The time, in seconds, that AWS OpsWorks Stacks will wait after triggering a Shutdown event before shutting down an instance.

          

          

        DelayUntilElbConnectionsDrained -> (boolean)

          

          Whether to enable Elastic Load Balancing connection draining. For more information, see `Connection Draining <http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/TerminologyandKeyConcepts.html#conn-drain>`_  

          

          

        

      

    

  

