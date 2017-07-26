[ :ref:`aws <cli:aws>` . :ref:`es <cli:aws es>` ]

.. _cli:aws es create-elasticsearch-domain:


***************************
create-elasticsearch-domain
***************************



===========
Description
===========



Creates a new Elasticsearch domain. For more information, see `Creating Elasticsearch Domains <http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-createupdatedomains.html#es-createdomains>`_ in the *Amazon Elasticsearch Service Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/es-2015-01-01/CreateElasticsearchDomain>`_


========
Synopsis
========

::

    create-elasticsearch-domain
  --domain-name <value>
  [--elasticsearch-version <value>]
  [--elasticsearch-cluster-config <value>]
  [--ebs-options <value>]
  [--access-policies <value>]
  [--snapshot-options <value>]
  [--advanced-options <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The name of the Elasticsearch domain that you are creating. Domain names are unique across the domains owned by an account within an AWS region. Domain names must start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

  

``--elasticsearch-version`` (string)


  String of format X.Y to specify version for the Elasticsearch domain eg. "1.5" or "2.3". For more information, see `Creating Elasticsearch Domains <http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-createupdatedomains.html#es-createdomains>`_ in the *Amazon Elasticsearch Service Developer Guide* .

  

``--elasticsearch-cluster-config`` (structure)


  Configuration options for an Elasticsearch domain. Specifies the instance type and number of instances in the domain cluster. 

  



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


  Options to enable, disable and specify the type and size of EBS storage volumes. 

  



Shorthand Syntax::

    EBSEnabled=boolean,VolumeType=string,VolumeSize=integer,Iops=integer




JSON Syntax::

  {
    "EBSEnabled": true|false,
    "VolumeType": "standard"|"gp2"|"io1",
    "VolumeSize": integer,
    "Iops": integer
  }



``--access-policies`` (string)


  IAM access policy as a JSON-formatted string.

  

``--snapshot-options`` (structure)


  Option to set time, in UTC format, of the daily automated snapshot. Default value is 0 hours. 

  



Shorthand Syntax::

    AutomatedSnapshotStartHour=integer




JSON Syntax::

  {
    "AutomatedSnapshotStartHour": integer
  }



``--advanced-options`` (map)


  Option to allow references to indices in an HTTP request body. Must be ``false`` when configuring access to individual sub-resources. By default, the value is ``true`` . See `Configuration Advanced Options <http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-createupdatedomains.html#es-createdomain-configure-advanced-options>`_ for more information.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DomainStatus -> (structure)

  

  The status of the newly created Elasticsearch domain. 

  

  DomainId -> (string)

    

    The unique identifier for the specified Elasticsearch domain.

    

    

  DomainName -> (string)

    

    The name of an Elasticsearch domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

    

    

  ARN -> (string)

    

    The Amazon resource name (ARN) of an Elasticsearch domain. See `Identifiers for IAM Entities <http://docs.aws.amazon.com/IAM/latest/UserGuide/index.html?Using_Identifiers.html>`_ in *Using AWS Identity and Access Management* for more information.

    

    

  Created -> (boolean)

    

    The domain creation status. ``True`` if the creation of an Elasticsearch domain is complete. ``False`` if domain creation is still in progress.

    

    

  Deleted -> (boolean)

    

    The domain deletion status. ``True`` if a delete request has been received for the domain but resource cleanup is still in progress. ``False`` if the domain has not been deleted. Once domain deletion is complete, the status of the domain is no longer returned.

    

    

  Endpoint -> (string)

    

    The Elasticsearch domain endpoint that you use to submit index and search requests.

    

    

  Processing -> (boolean)

    

    The status of the Elasticsearch domain configuration. ``True`` if Amazon Elasticsearch Service is processing configuration changes. ``False`` if the configuration is active.

    

    

  ElasticsearchVersion -> (string)

    

    

  ElasticsearchClusterConfig -> (structure)

    

    The type and number of instances in the domain cluster.

    

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

      

      

    

  EBSOptions -> (structure)

    

    The ``ebs-options`` for the specified domain. See `Configuring EBS-based Storage <http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-createupdatedomains.html#es-createdomain-configure-ebs>`_ for more information.

    

    EBSEnabled -> (boolean)

      

      Specifies whether EBS-based storage is enabled.

      

      

    VolumeType -> (string)

      

      Specifies the volume type for EBS-based storage.

      

      

    VolumeSize -> (integer)

      

      Integer to specify the size of an EBS volume.

      

      

    Iops -> (integer)

      

      Specifies the IOPD for a Provisioned IOPS EBS volume (SSD).

      

      

    

  AccessPolicies -> (string)

    

    IAM access policy as a JSON-formatted string.

    

    

  SnapshotOptions -> (structure)

    

    Specifies the status of the ``snapshot-options`` 

    

    AutomatedSnapshotStartHour -> (integer)

      

      Specifies the time, in UTC format, when the service takes a daily automated snapshot of the specified Elasticsearch domain. Default value is ``0`` hours.

      

      

    

  AdvancedOptions -> (map)

    

    Specifies the status of the ``advanced-options`` 

    

    key -> (string)

      

      

    value -> (string)

      

      

    

  

