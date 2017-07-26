[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache modify-cache-cluster:


********************
modify-cache-cluster
********************



===========
Description
===========



Modifies the settings for a cache cluster. You can use this operation to change one or more cluster configuration parameters by specifying the parameters and the new values.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/ModifyCacheCluster>`_


========
Synopsis
========

::

    modify-cache-cluster
  --cache-cluster-id <value>
  [--num-cache-nodes <value>]
  [--cache-node-ids-to-remove <value>]
  [--az-mode <value>]
  [--new-availability-zones <value>]
  [--cache-security-group-names <value>]
  [--security-group-ids <value>]
  [--preferred-maintenance-window <value>]
  [--notification-topic-arn <value>]
  [--cache-parameter-group-name <value>]
  [--notification-topic-status <value>]
  [--apply-immediately | --no-apply-immediately]
  [--engine-version <value>]
  [--auto-minor-version-upgrade | --no-auto-minor-version-upgrade]
  [--snapshot-retention-limit <value>]
  [--snapshot-window <value>]
  [--cache-node-type <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cache-cluster-id`` (string)


  The cache cluster identifier. This value is stored as a lowercase string.

  

``--num-cache-nodes`` (integer)


  The number of cache nodes that the cache cluster should have. If the value for ``NumCacheNodes`` is greater than the sum of the number of current cache nodes and the number of cache nodes pending creation (which may be zero), more nodes are added. If the value is less than the number of existing cache nodes, nodes are removed. If the value is equal to the number of current cache nodes, any pending add or remove requests are canceled.

   

  If you are removing cache nodes, you must use the ``CacheNodeIdsToRemove`` parameter to provide the IDs of the specific cache nodes to remove.

   

  For clusters running Redis, this value must be 1. For clusters running Memcached, this value must be between 1 and 20.

   

  .. note::

     

    Adding or removing Memcached cache nodes can be applied immediately or as a pending operation (see ``ApplyImmediately`` ).

     

    A pending operation to modify the number of cache nodes in a cluster during its maintenance window, whether by adding or removing nodes in accordance with the scale out architecture, is not queued. The customer's latest request to add or remove nodes to the cluster overrides any previous pending operations to modify the number of cache nodes in the cluster. For example, a request to remove 2 nodes would override a previous pending operation to remove 3 nodes. Similarly, a request to add 2 nodes would override a previous pending operation to remove 3 nodes and vice versa. As Memcached cache nodes may now be provisioned in different Availability Zones with flexible cache node placement, a request to add nodes does not automatically override a previous pending operation to add nodes. The customer can modify the previous pending operation to add more nodes or explicitly cancel the pending request and retry the new request. To cancel pending operations to modify the number of cache nodes in a cluster, use the ``modify-cache-cluster`` request and set ``NumCacheNodes`` equal to the number of cache nodes currently in the cache cluster.

     

  

``--cache-node-ids-to-remove`` (list)


  A list of cache node IDs to be removed. A node ID is a numeric identifier (0001, 0002, etc.). This parameter is only valid when ``NumCacheNodes`` is less than the existing number of cache nodes. The number of cache node IDs supplied in this parameter must match the difference between the existing number of cache nodes in the cluster or pending cache nodes, whichever is greater, and the value of ``NumCacheNodes`` in the request.

   

  For example: If you have 3 active cache nodes, 7 pending cache nodes, and the number of cache nodes in this ``ModifyCacheCluser`` call is 5, you must list 2 (7 - 5) cache node IDs to remove.

  



Syntax::

  "string" "string" ...



``--az-mode`` (string)


  Specifies whether the new nodes in this Memcached cache cluster are all created in a single Availability Zone or created across multiple Availability Zones.

   

  Valid values: ``single-az`` | ``cross-az`` .

   

  This option is only supported for Memcached cache clusters.

   

  .. note::

     

    You cannot specify ``single-az`` if the Memcached cache cluster already has cache nodes in different Availability Zones. If ``cross-az`` is specified, existing Memcached nodes remain in their current Availability Zone.

     

    Only newly created nodes are located in different Availability Zones. For instructions on how to move existing Memcached nodes to different Availability Zones, see the **Availability Zone Considerations** section of `Cache Node Considerations for Memcached <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheNode.Memcached.html>`_ .

     

  

  Possible values:

  
  *   ``single-az``

  
  *   ``cross-az``

  

  

``--new-availability-zones`` (list)


  The list of Availability Zones where the new Memcached cache nodes are created.

   

  This parameter is only valid when ``NumCacheNodes`` in the request is greater than the sum of the number of active cache nodes and the number of cache nodes pending creation (which may be zero). The number of Availability Zones supplied in this list must match the cache nodes being added in this request.

   

  This option is only supported on Memcached clusters.

   

  Scenarios:

   

   
  * **Scenario 1:** You have 3 active nodes and wish to add 2 nodes. Specify ``NumCacheNodes=5`` (3 + 2) and optionally specify two Availability Zones for the two new nodes. 
   
  * **Scenario 2:** You have 3 active nodes and 2 nodes pending creation (from the scenario 1 call) and want to add 1 more node. Specify ``NumCacheNodes=6`` ((3 + 2) + 1) and optionally specify an Availability Zone for the new node. 
   
  * **Scenario 3:** You want to cancel all pending operations. Specify ``NumCacheNodes=3`` to cancel all pending operations. 
   

   

  The Availability Zone placement of nodes pending creation cannot be modified. If you wish to cancel any nodes pending creation, add 0 nodes by setting ``NumCacheNodes`` to the number of current nodes.

   

  If ``cross-az`` is specified, existing Memcached nodes remain in their current Availability Zone. Only newly created nodes can be located in different Availability Zones. For guidance on how to move existing Memcached nodes to different Availability Zones, see the **Availability Zone Considerations** section of `Cache Node Considerations for Memcached <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheNode.Memcached.html>`_ .

   

   **Impact of new add/remove requests upon pending requests**  

   

   
  * Scenario-1 

     
    * Pending Action: Delete 
     
    * New Request: Delete 
     
    * Result: The new delete, pending or immediate, replaces the pending delete. 
     

   
   
  * Scenario-2 

     
    * Pending Action: Delete 
     
    * New Request: Create 
     
    * Result: The new create, pending or immediate, replaces the pending delete. 
     

   
   
  * Scenario-3 

     
    * Pending Action: Create 
     
    * New Request: Delete 
     
    * Result: The new delete, pending or immediate, replaces the pending create. 
     

   
   
  * Scenario-4 

     
    * Pending Action: Create 
     
    * New Request: Create 
     
    * Result: The new create is added to the pending create. 

    .. warning::

        **Important:** If the new create request is **Apply Immediately - Yes** , all creates are performed immediately. If the new create request is **Apply Immediately - No** , all creates are pending. 

     
     

   
   

  



Syntax::

  "string" "string" ...



``--cache-security-group-names`` (list)


  A list of cache security group names to authorize on this cache cluster. This change is asynchronously applied as soon as possible.

   

  You can use this parameter only with clusters that are created outside of an Amazon Virtual Private Cloud (Amazon VPC).

   

  Constraints: Must contain no more than 255 alphanumeric characters. Must not be "Default".

  



Syntax::

  "string" "string" ...



``--security-group-ids`` (list)


  Specifies the VPC Security Groups associated with the cache cluster.

   

  This parameter can be used only with clusters that are created in an Amazon Virtual Private Cloud (Amazon VPC).

  



Syntax::

  "string" "string" ...



``--preferred-maintenance-window`` (string)


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

  

``--notification-topic-arn`` (string)


  The Amazon Resource Name (ARN) of the Amazon SNS topic to which notifications are sent.

   

  .. note::

     

    The Amazon SNS topic owner must be same as the cache cluster owner.

     

  

``--cache-parameter-group-name`` (string)


  The name of the cache parameter group to apply to this cache cluster. This change is asynchronously applied as soon as possible for parameters when the ``ApplyImmediately`` parameter is specified as ``true`` for this request.

  

``--notification-topic-status`` (string)


  The status of the Amazon SNS notification topic. Notifications are sent only if the status is ``active`` .

   

  Valid values: ``active`` | ``inactive``  

  

``--apply-immediately`` | ``--no-apply-immediately`` (boolean)


  If ``true`` , this parameter causes the modifications in this request and any pending modifications to be applied, asynchronously and as soon as possible, regardless of the ``PreferredMaintenanceWindow`` setting for the cache cluster.

   

  If ``false`` , changes to the cache cluster are applied on the next maintenance reboot, or the next failure reboot, whichever occurs first.

   

  .. warning::

     

    If you perform a ``modify-cache-cluster`` before a pending modification is applied, the pending modification is replaced by the newer modification.

     

   

  Valid values: ``true`` | ``false``  

   

  Default: ``false``  

  

``--engine-version`` (string)


  The upgraded version of the cache engine to be run on the cache nodes.

   

   **Important:** You can upgrade to a newer engine version (see `Selecting a Cache Engine and Version <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/SelectEngine.html#VersionManagement>`_ ), but you cannot downgrade to an earlier engine version. If you want to use an earlier engine version, you must delete the existing cache cluster and create it anew with the earlier engine version. 

  

``--auto-minor-version-upgrade`` | ``--no-auto-minor-version-upgrade`` (boolean)


  This parameter is currently disabled.

  

``--snapshot-retention-limit`` (integer)


  The number of days for which ElastiCache retains automatic cache cluster snapshots before deleting them. For example, if you set ``SnapshotRetentionLimit`` to 5, a snapshot that was taken today is retained for 5 days before being deleted.

   

  .. note::

     

    If the value of ``SnapshotRetentionLimit`` is set to zero (0), backups are turned off.

     

  

``--snapshot-window`` (string)


  The daily time range (in UTC) during which ElastiCache begins taking a daily snapshot of your cache cluster. 

  

``--cache-node-type`` (string)


  A valid cache node type that you want to scale this cache cluster up to.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CacheCluster -> (structure)

  

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

    

    

  

