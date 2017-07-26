[ :ref:`aws <cli:aws>` . :ref:`es <cli:aws es>` ]

.. _cli:aws es describe-elasticsearch-domain-config:


************************************
describe-elasticsearch-domain-config
************************************



===========
Description
===========



Provides cluster configuration information about the specified Elasticsearch domain, such as the state, creation date, update version, and update date for cluster options.



========
Synopsis
========

::

    describe-elasticsearch-domain-config
  --domain-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  The Elasticsearch domain that you want to get information about.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DomainConfig -> (structure)

  

  The configuration information of the domain requested in the ``describe-elasticsearch-domain-config`` request.

  

  ElasticsearchClusterConfig -> (structure)

    

    Specifies the ``ElasticsearchClusterConfig`` for the Elasticsearch domain.

    

    Options -> (structure)

      

      Specifies the cluster configuration for the specified Elasticsearch domain.

      

      InstanceType -> (string)

        

        The instance type for an Elasticsearch cluster.

        

        

      InstanceCount -> (integer)

        

        The number of instances in the specified domain cluster.

        

        

      DedicatedMasterEnabled -> (boolean)

        

        A boolean value to indicate whether a dedicated master node is enabled. See `About Dedicated Master Nodes`_ for more information.

        

        

      ZoneAwarenessEnabled -> (boolean)

        

        A boolean value to indicate whether zone awareness is enabled. See `About Zone Awareness`_ for more information.

        

        

      DedicatedMasterType -> (string)

        

        The instance type for a dedicated master node.

        

        

      DedicatedMasterCount -> (integer)

        

        Total number of dedicated master nodes, active and on standby, for the cluster.

        

        

      

    Status -> (structure)

      

      Specifies the status of the configuration for the specified Elasticsearch domain.

      

      CreationDate -> (timestamp)

        

        Timestamp which tells the creation date for the entity.

        

        

      UpdateDate -> (timestamp)

        

        Timestamp which tells the last updated time for the entity.

        

        

      UpdateVersion -> (integer)

        

        Specifies the latest version for the entity.

        

        

      State -> (string)

        

        Provides the ``OptionState`` for the Elasticsearch domain.

        

        

      PendingDeletion -> (boolean)

        

        Indicates whether the Elasticsearch domain is being deleted.

        

        

      

    

  EBSOptions -> (structure)

    

    Specifies the ``EBSOptions`` for the Elasticsearch domain.

    

    Options -> (structure)

      

      Specifies the EBS options for the specified Elasticsearch domain.

      

      EBSEnabled -> (boolean)

        

        Specifies whether EBS-based storage is enabled.

        

        

      VolumeType -> (string)

        

        Specifies the volume type for EBS-based storage.

        

        

      VolumeSize -> (integer)

        

        Integer to specify the size of an EBS volume.

        

        

      Iops -> (integer)

        

        Specifies the IOPD for a Provisioned IOPS EBS volume (SSD).

        

        

      

    Status -> (structure)

      

      Specifies the status of the EBS options for the specified Elasticsearch domain.

      

      CreationDate -> (timestamp)

        

        Timestamp which tells the creation date for the entity.

        

        

      UpdateDate -> (timestamp)

        

        Timestamp which tells the last updated time for the entity.

        

        

      UpdateVersion -> (integer)

        

        Specifies the latest version for the entity.

        

        

      State -> (string)

        

        Provides the ``OptionState`` for the Elasticsearch domain.

        

        

      PendingDeletion -> (boolean)

        

        Indicates whether the Elasticsearch domain is being deleted.

        

        

      

    

  AccessPolicies -> (structure)

    

    IAM access policy as a JSON-formatted string.

    

    Options -> (string)

      

      The access policy configured for the Elasticsearch domain. Access policies may be resource-based, IP-based, or IAM-based. See `Configuring Access Policies`_ for more information.

      

      

    Status -> (structure)

      

      The status of the access policy for the Elasticsearch domain. See ``OptionStatus`` for the status information that's included. 

      

      CreationDate -> (timestamp)

        

        Timestamp which tells the creation date for the entity.

        

        

      UpdateDate -> (timestamp)

        

        Timestamp which tells the last updated time for the entity.

        

        

      UpdateVersion -> (integer)

        

        Specifies the latest version for the entity.

        

        

      State -> (string)

        

        Provides the ``OptionState`` for the Elasticsearch domain.

        

        

      PendingDeletion -> (boolean)

        

        Indicates whether the Elasticsearch domain is being deleted.

        

        

      

    

  SnapshotOptions -> (structure)

    

    Specifies the ``SnapshotOptions`` for the Elasticsearch domain.

    

    Options -> (structure)

      

      Specifies the daily snapshot options specified for the Elasticsearch domain.

      

      AutomatedSnapshotStartHour -> (integer)

        

        Specifies the time, in UTC format, when the service takes a daily automated snapshot of the specified Elasticsearch domain. Default value is ``0`` hours.

        

        

      

    Status -> (structure)

      

      Specifies the status of a daily automated snapshot.

      

      CreationDate -> (timestamp)

        

        Timestamp which tells the creation date for the entity.

        

        

      UpdateDate -> (timestamp)

        

        Timestamp which tells the last updated time for the entity.

        

        

      UpdateVersion -> (integer)

        

        Specifies the latest version for the entity.

        

        

      State -> (string)

        

        Provides the ``OptionState`` for the Elasticsearch domain.

        

        

      PendingDeletion -> (boolean)

        

        Indicates whether the Elasticsearch domain is being deleted.

        

        

      

    

  AdvancedOptions -> (structure)

    

    Specifies the ``AdvancedOptions`` for the domain. See `Configuring Advanced Options`_ for more information.

    

    Options -> (map)

      

      Specifies the status of advanced options for the specified Elasticsearch domain.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    Status -> (structure)

      

      Specifies the status of ``OptionStatus`` for advanced options for the specified Elasticsearch domain.

      

      CreationDate -> (timestamp)

        

        Timestamp which tells the creation date for the entity.

        

        

      UpdateDate -> (timestamp)

        

        Timestamp which tells the last updated time for the entity.

        

        

      UpdateVersion -> (integer)

        

        Specifies the latest version for the entity.

        

        

      State -> (string)

        

        Provides the ``OptionState`` for the Elasticsearch domain.

        

        

      PendingDeletion -> (boolean)

        

        Indicates whether the Elasticsearch domain is being deleted.

        

        

      

    

  



.. _Configuring Access Policies: http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-createupdatedomains.html#es-createdomain-configure-access-policies
.. _About Zone Awareness: http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-managedomains.html#es-managedomains-zoneawareness
.. _About Dedicated Master Nodes: http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-managedomains.html#es-managedomains-dedicatedmasternodes
.. _Configuring Advanced Options: http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-createupdatedomains.html#es-createdomain-configure-advanced-options
