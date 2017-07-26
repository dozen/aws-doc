[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache describe-cache-clusters:


***********************
describe-cache-clusters
***********************



===========
Description
===========



Returns information about all provisioned cache clusters if no cache cluster identifier is specified, or about a specific cache cluster if a cache cluster identifier is supplied.

 

By default, abbreviated information about the cache clusters is returned. You can use the optional *ShowCacheNodeInfo* flag to retrieve detailed information about the cache nodes associated with the cache clusters. These details include the DNS address and port for the cache node endpoint.

 

If the cluster is in the *creating* state, only cluster-level information is displayed until all of the nodes are successfully provisioned.

 

If the cluster is in the *deleting* state, only cluster-level information is displayed.

 

If cache nodes are currently being added to the cache cluster, node endpoint information and creation time for the additional nodes are not displayed until they are completely provisioned. When the cache cluster state is *available* , the cluster is ready for use.

 

If cache nodes are currently being removed from the cache cluster, no endpoint information for the removed nodes is displayed.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/DescribeCacheClusters>`_


``describe-cache-clusters`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``CacheClusters``


========
Synopsis
========

::

    describe-cache-clusters
  [--cache-cluster-id <value>]
  [--show-cache-node-info | --no-show-cache-node-info]
  [--show-cache-clusters-not-in-replication-groups | --no-show-cache-clusters-not-in-replication-groups]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cache-cluster-id`` (string)


  The user-supplied cluster identifier. If this parameter is specified, only information about that specific cache cluster is returned. This parameter isn't case sensitive.

  

``--show-cache-node-info`` | ``--no-show-cache-node-info`` (boolean)


  An optional flag that can be included in the ``DescribeCacheCluster`` request to retrieve information about the individual cache nodes.

  

``--show-cache-clusters-not-in-replication-groups`` | ``--no-show-cache-clusters-not-in-replication-groups`` (boolean)


  An optional flag that can be included in the ``DescribeCacheCluster`` request to show only nodes (API/CLI: clusters) that are not members of a replication group. In practice, this mean Memcached and single node Redis clusters.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Marker -> (string)

  

  Provides an identifier to allow retrieval of paginated results.

  

  

CacheClusters -> (list)

  

  A list of cache clusters. Each item in the list contains detailed information about one cache cluster.

  

  (structure)

    

    Contains all of the attributes of a specific cache cluster.

    

    CacheClusterId -> (string)

      

      The user-supplied identifier of the cache cluster. This identifier is a unique key that identifies a cache cluster.

      

      

    ConfigurationEndpoint -> (structure)

      

      Represents a Memcached cluster endpoint which, if Automatic Discovery is enabled on the cluster, can be used by an application to connect to any node in the cluster. The configuration endpoint will always have ``.cfg`` in it.

       

      Example: ``mem-3.9dvc4r.cfg.usw2.cache.amazonaws.com:11211``  

      

      Address -> (string)

        

        The DNS hostname of the cache node.

        

        

      Port -> (integer)

        

        The port number that the cache engine is listening on.

        

        

      

    ClientDownloadLandingPage -> (string)

      

      The URL of the web page where you can download the latest ElastiCache client library.

      

      

    CacheNodeType -> (string)

      

      The name of the compute and memory capacity node type for the cache cluster.

       

      Valid node types are as follows:

       

       
      * General purpose: 

         
        * Current generation: ``cache.t2.micro`` , ``cache.t2.small`` , ``cache.t2.medium`` , ``cache.m3.medium`` , ``cache.m3.large`` , ``cache.m3.xlarge`` , ``cache.m3.2xlarge`` , ``cache.m4.large`` , ``cache.m4.xlarge`` , ``cache.m4.2xlarge`` , ``cache.m4.4xlarge`` , ``cache.m4.10xlarge``   
         
        * Previous generation: ``cache.t1.micro`` , ``cache.m1.small`` , ``cache.m1.medium`` , ``cache.m1.large`` , ``cache.m1.xlarge``   
         

       
       
      * Compute optimized: ``cache.c1.xlarge``   
       
      * Memory optimized: 

         
        * Current generation: ``cache.r3.large`` , ``cache.r3.xlarge`` , ``cache.r3.2xlarge`` , ``cache.r3.4xlarge`` , ``cache.r3.8xlarge``   
         
        * Previous generation: ``cache.m2.xlarge`` , ``cache.m2.2xlarge`` , ``cache.m2.4xlarge``   
         

       
       

       

       **Notes:**  

       

       
      * All T2 instances are created in an Amazon Virtual Private Cloud (Amazon VPC). 
       
      * Redis backup/restore is not supported for Redis (cluster mode disabled) T1 and T2 instances. Backup/restore is supported on Redis (cluster mode enabled) T2 instances. 
       
      * Redis Append-only files (AOF) functionality is not supported for T1 or T2 instances. 
       

       

      For a complete listing of node types and specifications, see `Amazon ElastiCache Product Features and Details <http://aws.amazon.com/elasticache/details>`_ and either `Cache Node Type-Specific Parameters for Memcached <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheParameterGroups.Memcached.html#ParameterGroups.Memcached.NodeSpecific>`_ or `Cache Node Type-Specific Parameters for Redis <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheParameterGroups.Redis.html#ParameterGroups.Redis.NodeSpecific>`_ .

      

      

    Engine -> (string)

      

      The name of the cache engine (``memcached`` or ``redis`` ) to be used for this cache cluster.

      

      

    EngineVersion -> (string)

      

      The version of the cache engine that is used in this cache cluster.

      

      

    CacheClusterStatus -> (string)

      

      The current state of this cache cluster, one of the following values: ``available`` , ``creating`` , ``deleted`` , ``deleting`` , ``incompatible-network`` , ``modifying`` , ``rebooting cache cluster nodes`` , ``restore-failed`` , or ``snapshotting`` .

      

      

    NumCacheNodes -> (integer)

      

      The number of cache nodes in the cache cluster.

       

      For clusters running Redis, this value must be 1. For clusters running Memcached, this value must be between 1 and 20.

      

      

    PreferredAvailabilityZone -> (string)

      

      The name of the Availability Zone in which the cache cluster is located or "Multiple" if the cache nodes are located in different Availability Zones.

      

      

    CacheClusterCreateTime -> (timestamp)

      

      The date and time when the cache cluster was created.

      

      

    PreferredMaintenanceWindow -> (string)

      

      Specifies the weekly time range during which maintenance on the cluster is performed. It is specified as a range in the format ddd:hh24:mi-ddd:hh24:mi (24H Clock UTC). The minimum maintenance window is a 60 minute period.

       

      Valid values for ``ddd`` are:

       

       
      * ``sun``   
       
      * ``mon``   
       
      * ``tue``   
       
      * ``wed``   
       
      * ``thu``   
       
      * ``fri``   
       
      * ``sat``   
       

       

      Example: ``sun:23:00-mon:01:30``  

      

      

    PendingModifiedValues -> (structure)

      

      A group of settings that are applied to the cache cluster in the future, or that are currently being applied.

      

      NumCacheNodes -> (integer)

        

        The new number of cache nodes for the cache cluster.

         

        For clusters running Redis, this value must be 1. For clusters running Memcached, this value must be between 1 and 20.

        

        

      CacheNodeIdsToRemove -> (list)

        

        A list of cache node IDs that are being removed (or will be removed) from the cache cluster. A node ID is a numeric identifier (0001, 0002, etc.).

        

        (string)

          

          

        

      EngineVersion -> (string)

        

        The new cache engine version that the cache cluster runs.

        

        

      CacheNodeType -> (string)

        

        The cache node type that this cache cluster or replication group is scaled to.

        

        

      

    NotificationConfiguration -> (structure)

      

      Describes a notification topic and its status. Notification topics are used for publishing ElastiCache events to subscribers using Amazon Simple Notification Service (SNS).

      

      TopicArn -> (string)

        

        The Amazon Resource Name (ARN) that identifies the topic.

        

        

      TopicStatus -> (string)

        

        The current state of the topic.

        

        

      

    CacheSecurityGroups -> (list)

      

      A list of cache security group elements, composed of name and status sub-elements.

      

      (structure)

        

        Represents a cache cluster's status within a particular cache security group.

        

        CacheSecurityGroupName -> (string)

          

          The name of the cache security group.

          

          

        Status -> (string)

          

          The membership status in the cache security group. The status changes when a cache security group is modified, or when the cache security groups assigned to a cache cluster are modified.

          

          

        

      

    CacheParameterGroup -> (structure)

      

      Status of the cache parameter group.

      

      CacheParameterGroupName -> (string)

        

        The name of the cache parameter group.

        

        

      ParameterApplyStatus -> (string)

        

        The status of parameter updates.

        

        

      CacheNodeIdsToReboot -> (list)

        

        A list of the cache node IDs which need to be rebooted for parameter changes to be applied. A node ID is a numeric identifier (0001, 0002, etc.).

        

        (string)

          

          

        

      

    CacheSubnetGroupName -> (string)

      

      The name of the cache subnet group associated with the cache cluster.

      

      

    CacheNodes -> (list)

      

      A list of cache nodes that are members of the cache cluster.

      

      (structure)

        

        Represents an individual cache node within a cache cluster. Each cache node runs its own instance of the cluster's protocol-compliant caching software - either Memcached or Redis.

         

        Valid node types are as follows:

         

         
        * General purpose: 

           
          * Current generation: ``cache.t2.micro`` , ``cache.t2.small`` , ``cache.t2.medium`` , ``cache.m3.medium`` , ``cache.m3.large`` , ``cache.m3.xlarge`` , ``cache.m3.2xlarge`` , ``cache.m4.large`` , ``cache.m4.xlarge`` , ``cache.m4.2xlarge`` , ``cache.m4.4xlarge`` , ``cache.m4.10xlarge``   
           
          * Previous generation: ``cache.t1.micro`` , ``cache.m1.small`` , ``cache.m1.medium`` , ``cache.m1.large`` , ``cache.m1.xlarge``   
           

         
         
        * Compute optimized: ``cache.c1.xlarge``   
         
        * Memory optimized: 

           
          * Current generation: ``cache.r3.large`` , ``cache.r3.xlarge`` , ``cache.r3.2xlarge`` , ``cache.r3.4xlarge`` , ``cache.r3.8xlarge``   
           
          * Previous generation: ``cache.m2.xlarge`` , ``cache.m2.2xlarge`` , ``cache.m2.4xlarge``   
           

         
         

         

         **Notes:**  

         

         
        * All T2 instances are created in an Amazon Virtual Private Cloud (Amazon VPC). 
         
        * Redis backup/restore is not supported for Redis (cluster mode disabled) T1 and T2 instances. Backup/restore is supported on Redis (cluster mode enabled) T2 instances. 
         
        * Redis Append-only files (AOF) functionality is not supported for T1 or T2 instances. 
         

         

        For a complete listing of node types and specifications, see `Amazon ElastiCache Product Features and Details <http://aws.amazon.com/elasticache/details>`_ and either `Cache Node Type-Specific Parameters for Memcached <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheParameterGroups.Memcached.html#ParameterGroups.Memcached.NodeSpecific>`_ or `Cache Node Type-Specific Parameters for Redis <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheParameterGroups.Redis.html#ParameterGroups.Redis.NodeSpecific>`_ .

        

        CacheNodeId -> (string)

          

          The cache node identifier. A node ID is a numeric identifier (0001, 0002, etc.). The combination of cluster ID and node ID uniquely identifies every cache node used in a customer's AWS account.

          

          

        CacheNodeStatus -> (string)

          

          The current state of this cache node.

          

          

        CacheNodeCreateTime -> (timestamp)

          

          The date and time when the cache node was created.

          

          

        Endpoint -> (structure)

          

          The hostname for connecting to this cache node.

          

          Address -> (string)

            

            The DNS hostname of the cache node.

            

            

          Port -> (integer)

            

            The port number that the cache engine is listening on.

            

            

          

        ParameterGroupStatus -> (string)

          

          The status of the parameter group applied to this cache node.

          

          

        SourceCacheNodeId -> (string)

          

          The ID of the primary node to which this read replica node is synchronized. If this field is empty, this node is not associated with a primary cache cluster.

          

          

        CustomerAvailabilityZone -> (string)

          

          The Availability Zone where this node was created and now resides.

          

          

        

      

    AutoMinorVersionUpgrade -> (boolean)

      

      This parameter is currently disabled.

      

      

    SecurityGroups -> (list)

      

      A list of VPC Security Groups associated with the cache cluster.

      

      (structure)

        

        Represents a single cache security group and its status.

        

        SecurityGroupId -> (string)

          

          The identifier of the cache security group.

          

          

        Status -> (string)

          

          The status of the cache security group membership. The status changes whenever a cache security group is modified, or when the cache security groups assigned to a cache cluster are modified.

          

          

        

      

    ReplicationGroupId -> (string)

      

      The replication group to which this cache cluster belongs. If this field is empty, the cache cluster is not associated with any replication group.

      

      

    SnapshotRetentionLimit -> (integer)

      

      The number of days for which ElastiCache retains automatic cache cluster snapshots before deleting them. For example, if you set ``SnapshotRetentionLimit`` to 5, a snapshot that was taken today is retained for 5 days before being deleted.

       

      .. warning::

         

        If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.

         

      

      

    SnapshotWindow -> (string)

      

      The daily time range (in UTC) during which ElastiCache begins taking a daily snapshot of your cache cluster.

       

      Example: ``05:00-09:00``  

      

      

    

  

