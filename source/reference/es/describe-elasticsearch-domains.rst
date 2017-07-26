[ :ref:`aws <cli:aws>` . :ref:`es <cli:aws es>` ]

.. _cli:aws es describe-elasticsearch-domains:


******************************
describe-elasticsearch-domains
******************************



===========
Description
===========



Returns domain configuration information about the specified Elasticsearch domains, including the domain ID, domain endpoint, and domain ARN.



========
Synopsis
========

::

    describe-elasticsearch-domains
  --domain-names <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-names`` (list)


  The Elasticsearch domains for which you want information.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DomainStatusList -> (list)

  

  The status of the domains requested in the ``describe-elasticsearch-domains`` request.

  

  (structure)

    

    The current status of an Elasticsearch domain.

    

    DomainId -> (string)

      

      The unique identifier for the specified Elasticsearch domain.

      

      

    DomainName -> (string)

      

      The name of an Elasticsearch domain. Domain names are unique across the domains owned by an account within an AWS region. Domain names start with a letter or number and can contain the following characters: a-z (lowercase), 0-9, and - (hyphen).

      

      

    ARN -> (string)

      

      The Amazon resource name (ARN) of an Elasticsearch domain. See `Identifiers for IAM Entities`_ in *Using AWS Identity and Access Management* for more information.

      

      

    Created -> (boolean)

      

      The domain creation status. ``True`` if the creation of an Elasticsearch domain is complete. ``False`` if domain creation is still in progress.

      

      

    Deleted -> (boolean)

      

      The domain deletion status. ``True`` if a delete request has been received for the domain but resource cleanup is still in progress. ``False`` if the domain has not been deleted. Once domain deletion is complete, the status of the domain is no longer returned.

      

      

    Endpoint -> (string)

      

      The Elasticsearch domain endpoint that you use to submit index and search requests.

      

      

    Processing -> (boolean)

      

      The status of the Elasticsearch domain configuration. ``True`` if Amazon Elasticsearch Service is processing configuration changes. ``False`` if the configuration is active.

      

      

    ElasticsearchClusterConfig -> (structure)

      

      The type and number of instances in the domain cluster.

      

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

        

        

      

    EBSOptions -> (structure)

      

      The ``EBSOptions`` for the specified domain. See `Configuring EBS-based Storage`_ for more information.

      

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

      

      Specifies the status of the ``SnapshotOptions`` 

      

      AutomatedSnapshotStartHour -> (integer)

        

        Specifies the time, in UTC format, when the service takes a daily automated snapshot of the specified Elasticsearch domain. Default value is ``0`` hours.

        

        

      

    AdvancedOptions -> (map)

      

      Specifies the status of the ``AdvancedOptions`` 

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    

  



.. _Configuring EBS-based Storage: http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-createupdatedomains.html#es-createdomain-configure-ebs
.. _Identifiers for IAM Entities: http://docs.aws.amazon.com/IAM/latest/UserGuide/index.html?Using_Identifiers.html
.. _About Zone Awareness: http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-managedomains.html#es-managedomains-zoneawareness
.. _About Dedicated Master Nodes: http://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-managedomains.html#es-managedomains-dedicatedmasternodes
