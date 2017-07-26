[ :ref:`aws <cli:aws>` . :ref:`es <cli:aws es>` ]

.. _cli:aws es update-elasticsearch-domain-config:


**********************************
update-elasticsearch-domain-config
**********************************



===========
Description
===========



Modifies the cluster configuration of the specified Elasticsearch domain, setting as setting the instance type and the number of instances. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/es-2015-01-01/UpdateElasticsearchDomainConfig>`_


========
Synopsis
========

::

    update-elasticsearch-domain-config
  --domain-name <value>
  [--elasticsearch-cluster-config <value>]
  [--ebs-options <value>]
  [--snapshot-options <value>]
  [--advanced-options <value>]
  [--access-policies <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The name of the Elasticsearch domain that you are updating. 

  

``--elasticsearch-cluster-config`` (structure)


  The type and number of instances to instantiate for the domain cluster.

  



Shorthand Syntax::

    InstanceType=string,InstanceCount=integer,DedicatedMasterEnabled=boolean,ZoneAwarenessEnabled=boolean,DedicatedMasterType=string,DedicatedMasterCount=integer




JSON Syntax::

  {
    "InstanceType": "m3.medium.elasticsearch"|"m3.large.elasticsearch"|"m3.xlarge.elasticsearch"|"m3.2xlarge.elasticsearch"|"m4.large.elasticsearch"|"m4.xlarge.elasticsearch"|"m4.2xlarge.elasticsearch"|"m4.4xlarge.elasticsearch"|"m4.10xlarge.elasticsearch"|"t2.micro.elasticsearch"|"t2.small.elasticsearch"|"t2.medium.elasticsearch"|"r3.large.elasticsearch"|"r3.xlarge.elasticsearch"|"r3.2xlarge.elasticsearch"|"r3.4xlarge.elasticsearch"|"r3.8xlarge.elasticsearch"|"i2.xlarge.elasticsearch"|"i2.2xlarge.elasticsearch"|"d2.xlarge.elasticsearch"|"d2.2xlarge.elasticsearch"|"d2.4xlarge.elasticsearch"|"d2.8xlarge.elasticsearch"|"c4.large.elasticsearch"|"c4.xlarge.elasticsearch"|"c4.2xlarge.elasticsearch"|"c4.4xlarge.elasticsearch"|"c4.8xlarge.elasticsearch"|"r4.large.elasticsearch"|"r4.xlarge.elasticsearch"|"r4.2xlarge.elasticsearch"|"r4.4xlarge.elasticsearch"|"r4.8xlarge.elasticsearch"|"r4.16xlarge.elasticsearch",
    "InstanceCount": integer,
    "DedicatedMasterEnabled": true|false,
    "ZoneAwarenessEnabled": true|false,
    "DedicatedMasterType": "m3.medium.elasticsearch"|"m3.large.elasticsearch"|"m3.xlarge.elasticsearch"|"m3.2xlarge.elasticsearch"|"m4.large.elasticsearch"|"m4.xlarge.elasticsearch"|"m4.2xlarge.elasticsearch"|"m4.4xlarge.elasticsearch"|"m4.10xlarge.elasticsearch"|"t2.micro.elasticsearch"|"t2.small.elasticsearch"|"t2.medium.elasticsearch"|"r3.large.elasticsearch"|"r3.xlarge.elasticsearch"|"r3.2xlarge.elasticsearch"|"r3.4xlarge.elasticsearch"|"r3.8xlarge.elasticsearch"|"i2.xlarge.elasticsearch"|"i2.2xlarge.elasticsearch"|"d2.xlarge.elasticsearch"|"d2.2xlarge.elasticsearch"|"d2.4xlarge.elasticsearch"|"d2.8xlarge.elasticsearch"|"c4.large.elasticsearch"|"c4.xlarge.elasticsearch"|"c4.2xlarge.elasticsearch"|"c4.4xlarge.elasticsearch"|"c4.8xlarge.elasticsearch"|"r4.large.elasticsearch"|"r4.xlarge.elasticsearch"|"r4.2xlarge.elasticsearch"|"r4.4xlarge.elasticsearch"|"r4.8xlarge.elasticsearch"|"r4.16xlarge.elasticsearch",
    "DedicatedMasterCount": integer
  }



``--ebs-options`` (structure)


  Specify the type and size of the EBS volume that you want to use. 

  



Shorthand Syntax::

    EBSEnabled=boolean,VolumeType=string,VolumeSize=integer,Iops=integer




JSON Syntax::

  {
    "EBSEnabled": true|false,
    "VolumeType": "standard"|"gp2"|"io1",
    "VolumeSize": integer,
    "Iops": integer
  }



``--snapshot-options`` (structure)


  Option to set the time, in UTC format, for the daily automated snapshot. Default value is ``0`` hours. 

  



Shorthand Syntax::

    AutomatedSnapshotStartHour=integer




JSON Syntax::

  {
    "AutomatedSnapshotStartHour": integer
  }



``--advanced-options`` (map)


  Modifies the advanced option to allow references to indices in an HTTP request body. Must be ``false`` when configuring access to individual sub-resources. By default, the value is ``true`` . See `Configuration Advanced Options <http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-createupdatedomains.html#es-createdomain-configure-advanced-options>`_ for more information.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--access-policies`` (string)


  IAM access policy as a JSON-formatted string.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DomainConfig -> (structure)

  

  The status of the updated Elasticsearch domain. 

  

  ElasticsearchVersion -> (structure)

    

    String of format X.Y to specify version for the Elasticsearch domain.

    

    Options -> (string)

      

      Specifies the Elasticsearch version for the specified Elasticsearch domain.

      

      

    Status -> (structure)

      

      Specifies the status of the Elasticsearch version options for the specified Elasticsearch domain.

      

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

        

        

      

    

  ElasticsearchClusterConfig -> (structure)

    

    Specifies the ``elasticsearch-cluster-config`` for the Elasticsearch domain.

    

    Options -> (structure)

      

      Specifies the cluster configuration for the specified Elasticsearch domain.

      

      InstanceType -> (string)

        

        The instance type for an Elasticsearch cluster.

        

        

      InstanceCount -> (integer)

        

        The number of instances in the specified domain cluster.

        

        

      DedicatedMasterEnabled -> (boolean)

        

        A boolean value to indicate whether a dedicated master node is enabled. See `About Dedicated Master Nodes <http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-managedomains.html#es-managedomains-dedicatedmasternodes>`_ for more information.

        

        

      ZoneAwarenessEnabled -> (boolean)

        

        A boolean value to indicate whether zone awareness is enabled. See `About Zone Awareness <http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-managedomains.html#es-managedomains-zoneawareness>`_ for more information.

        

        

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

    

    Specifies the ``ebs-options`` for the Elasticsearch domain.

    

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

      

      The access policy configured for the Elasticsearch domain. Access policies may be resource-based, IP-based, or IAM-based. See `Configuring Access Policies <http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-createupdatedomains.html#es-createdomain-configure-access-policies>`_ for more information.

      

      

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

    

    Specifies the ``snapshot-options`` for the Elasticsearch domain.

    

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

    

    Specifies the ``advanced-options`` for the domain. See `Configuring Advanced Options <http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-createupdatedomains.html#es-createdomain-configure-advanced-options>`_ for more information.

    

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

        

        

      

    

  

