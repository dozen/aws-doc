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

   

  You must specify at least one of the parameters.

   

 

**Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    describe-layers
  [--stack-id <value>]
  [--layer-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe a stack's layers**

The following ``describe-layers`` commmand describes the layers in a specified stack::

  aws opsworks --region us-east-1 describe-layers --stack-id 38ee91e2-abdc-4208-a107-0b7168b3cc7a

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

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

       

      For the ``HaproxyStatsPassword`` , ``MysqlRootPassword`` , and ``GangliaPassword`` attributes, AWS OpsWorks returns ``*****FILTERED*****`` instead of the actual value

       

      For an ECS Cluster layer, AWS OpsWorks the ``EcsClusterArn`` attribute is set to the cluster's ARN.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    CustomInstanceProfileArn -> (string)

      

      The ARN of the default IAM profile to be used for the layer's EC2 instances. For more information about IAM ARNs, see `Using Identifiers`_ .

      

      

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

          

          The volume `RAID level`_ .

          

          

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

      

      Whether to automatically assign an `Elastic IP address`_ to the layer's instances. For more information, see `How to Edit a Layer`_ .

      

      

    AutoAssignPublicIps -> (boolean)

      

      For stacks that are running in a VPC, whether to automatically assign a public IP address to the layer's instances. For more information, see `How to Edit a Layer`_ .

      

      

    DefaultRecipes -> (structure)

      

      AWS OpsWorks supports five lifecycle events: **setup** , **configuration** , **deploy** , **undeploy** , and **shutdown** . For each layer, AWS OpsWorks runs a set of standard recipes for each event. In addition, you can provide custom recipes for any or all layers and events. AWS OpsWorks runs custom event recipes after the standard recipes. ``LayerCustomRecipes`` specifies the custom recipes for a particular layer to be run in response to each of the five events. 

       

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

          

          The time, in seconds, that AWS OpsWorks will wait after triggering a Shutdown event before shutting down an instance.

          

          

        DelayUntilElbConnectionsDrained -> (boolean)

          

          Whether to enable Elastic Load Balancing connection draining. For more information, see `Connection Draining`_ 

          

          

        

      

    

  



.. _RAID level: http://en.wikipedia.org/wiki/Standard_RAID_levels
.. _Using Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _Connection Draining: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/TerminologyandKeyConcepts.html#conn-drain
.. _Elastic IP address: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html
.. _How to Edit a Layer: http://docs.aws.amazon.com/opsworks/latest/userguide/workinglayers-basics-edit.html
.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
