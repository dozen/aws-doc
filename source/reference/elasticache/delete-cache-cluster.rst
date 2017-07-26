[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache delete-cache-cluster:


********************
delete-cache-cluster
********************



===========
Description
===========



The *delete-cache-cluster* action deletes a previously provisioned cache cluster. *delete-cache-cluster* deletes all associated cache nodes, node endpoints and the cache cluster itself. When you receive a successful response from this action, Amazon ElastiCache immediately begins deleting the cache cluster; you cannot cancel or revert this action.

 

This API cannot be used to delete a cache cluster that is the last read replica of a replication group that has Multi-AZ mode enabled.



========
Synopsis
========

::

    delete-cache-cluster
  --cache-cluster-id <value>
  [--final-snapshot-identifier <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cache-cluster-id`` (string)


  The cache cluster identifier for the cluster to be deleted. This parameter is not case sensitive.

  

``--final-snapshot-identifier`` (string)


  The user-supplied name of a final cache cluster snapshot. This is the unique name that identifies the snapshot. ElastiCache creates the snapshot, and then deletes the cache cluster immediately afterward.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

CacheCluster -> (structure)

  

  Contains all of the attributes of a specific cache cluster.

  

  CacheClusterId -> (string)

    

    The user-supplied identifier of the cache cluster. This identifier is a unique key that identifies a cache cluster.

    

    

  ConfigurationEndpoint -> (structure)

    

    Represents the information required for client programs to connect to a cache node.

    

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

       
      * Current generation: ``cache.t2.micro`` , ``cache.t2.small`` , ``cache.t2.medium`` , ``cache.m3.medium`` , ``cache.m3.large`` , ``cache.m3.xlarge`` , ``cache.m3.2xlarge`` 
       
      * Previous generation: ``cache.t1.micro`` , ``cache.m1.small`` , ``cache.m1.medium`` , ``cache.m1.large`` , ``cache.m1.xlarge`` 
       

    
     
    * Compute optimized: ``cache.c1.xlarge`` 
     
    * Memory optimized 

       
      * Current generation: ``cache.r3.large`` , ``cache.r3.xlarge`` , ``cache.r3.2xlarge`` , ``cache.r3.4xlarge`` , ``cache.r3.8xlarge`` 
       
      * Previous generation: ``cache.m2.xlarge`` , ``cache.m2.2xlarge`` , ``cache.m2.4xlarge`` 
       

    
     

     

    **Notes:** 

     

     
    * All t2 instances are created in an Amazon Virtual Private Cloud (VPC).
     
    * Redis backup/restore is not supported for t2 instances.
     
    * Redis Append-only files (AOF) functionality is not supported for t1 or t2 instances.
     

     

    For a complete listing of cache node types and specifications, see `Amazon ElastiCache Product Features and Details`_ and `Cache Node Type-Specific Parameters for Memcached`_ or `Cache Node Type-Specific Parameters for Redis`_ . 

    

    

  Engine -> (string)

    

    The name of the cache engine (*memcached* or *redis* ) to be used for this cache cluster.

    

    

  EngineVersion -> (string)

    

    The version of the cache engine version that is used in this cache cluster.

    

    

  CacheClusterStatus -> (string)

    

    The current state of this cache cluster, one of the following values: *available* , *creating* , *deleted* , *deleting* , *incompatible-network* , *modifying* , *rebooting cache cluster nodes* , *restore-failed* , or *snapshotting* .

    

    

  NumCacheNodes -> (integer)

    

    The number of cache nodes in the cache cluster.

     

    For clusters running Redis, this value must be 1. For clusters running Memcached, this value must be between 1 and 20.

    

    

  PreferredAvailabilityZone -> (string)

    

    The name of the Availability Zone in which the cache cluster is located or "Multiple" if the cache nodes are located in different Availability Zones.

    

    

  CacheClusterCreateTime -> (timestamp)

    

    The date and time when the cache cluster was created.

    

    

  PreferredMaintenanceWindow -> (string)

    

    Specifies the weekly time range during which maintenance on the cache cluster is performed. It is specified as a range in the format ddd:hh24:mi-ddd:hh24:mi (24H Clock UTC). The minimum maintenance window is a 60 minute period. Valid values for ``ddd`` are:

     

     
    * ``sun`` 
     
    * ``mon`` 
     
    * ``tue`` 
     
    * ``wed`` 
     
    * ``thu`` 
     
    * ``fri`` 
     
    * ``sat`` 
     

     

    Example: ``sun:05:00-sun:09:00`` 

    

    

  PendingModifiedValues -> (structure)

    

    A group of settings that will be applied to the cache cluster in the future, or that are currently being applied.

    

    NumCacheNodes -> (integer)

      

      The new number of cache nodes for the cache cluster.

       

      For clusters running Redis, this value must be 1. For clusters running Memcached, this value must be between 1 and 20.

      

      

    CacheNodeIdsToRemove -> (list)

      

      A list of cache node IDs that are being removed (or will be removed) from the cache cluster. A node ID is a numeric identifier (0001, 0002, etc.).

      

      (string)

        

        

      

    EngineVersion -> (string)

      

      The new cache engine version that the cache cluster will run.

      

      

    

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

    

    The status of the cache parameter group.

    

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

         
        * Current generation: ``cache.t2.micro`` , ``cache.t2.small`` , ``cache.t2.medium`` , ``cache.m3.medium`` , ``cache.m3.large`` , ``cache.m3.xlarge`` , ``cache.m3.2xlarge`` 
         
        * Previous generation: ``cache.t1.micro`` , ``cache.m1.small`` , ``cache.m1.medium`` , ``cache.m1.large`` , ``cache.m1.xlarge`` 
         

      
       
      * Compute optimized: ``cache.c1.xlarge`` 
       
      * Memory optimized 

         
        * Current generation: ``cache.r3.large`` , ``cache.r3.xlarge`` , ``cache.r3.2xlarge`` , ``cache.r3.4xlarge`` , ``cache.r3.8xlarge`` 
         
        * Previous generation: ``cache.m2.xlarge`` , ``cache.m2.2xlarge`` , ``cache.m2.4xlarge`` 
         

      
       

       

      **Notes:** 

       

       
      * All t2 instances are created in an Amazon Virtual Private Cloud (VPC).
       
      * Redis backup/restore is not supported for t2 instances.
       
      * Redis Append-only files (AOF) functionality is not supported for t1 or t2 instances.
       

       

      For a complete listing of cache node types and specifications, see `Amazon ElastiCache Product Features and Details`_ and `Cache Node Type-Specific Parameters for Memcached`_ or `Cache Node Type-Specific Parameters for Redis`_ . 

      

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

        

        The ID of the primary node to which this read replica node is synchronized. If this field is empty, then this node is not associated with a primary cache cluster.

        

        

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

    

    The number of days for which ElastiCache will retain automatic cache cluster snapshots before deleting them. For example, if you set *SnapshotRetentionLimit* to 5, then a snapshot that was taken today will be retained for 5 days before being deleted.

     

    **Important** If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.

    

    

  SnapshotWindow -> (string)

    

    The daily time range (in UTC) during which ElastiCache will begin taking a daily snapshot of your cache cluster.

     

    Example: ``05:00-09:00`` 

    

    

  



.. _Cache Node Type-Specific Parameters for Memcached: http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheParameterGroups.Memcached.html#CacheParameterGroups.Memcached.NodeSpecific
.. _Amazon ElastiCache Product Features and Details: http://aws.amazon.com/elasticache/details
.. _Cache Node Type-Specific Parameters for Redis: http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheParameterGroups.Redis.html#CacheParameterGroups.Redis.NodeSpecific
