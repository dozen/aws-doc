[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache create-replication-group:


************************
create-replication-group
************************



===========
Description
===========



Creates a Redis (cluster mode disabled) or a Redis (cluster mode enabled) replication group.

 

A Redis (cluster mode disabled) replication group is a collection of cache clusters, where one of the cache clusters is a read/write primary and the others are read-only replicas. Writes to the primary are asynchronously propagated to the replicas.

 

A Redis (cluster mode enabled) replication group is a collection of 1 to 15 node groups (shards). Each node group (shard) has one read/write primary node and up to 5 read-only replica nodes. Writes to the primary are asynchronously propagated to the replicas. Redis (cluster mode enabled) replication groups partition the data across node groups (shards).

 

When a Redis (cluster mode disabled) replication group has been successfully created, you can add one or more read replicas to it, up to a total of 5 read replicas. You cannot alter a Redis (cluster mode enabled) replication group after it has been created. However, if you need to increase or decrease the number of node groups (console: shards), you can avail yourself of ElastiCache for Redis' enhanced backup and restore. For more information, see `Restoring From a Backup with Cluster Resizing <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/backups-restoring.html>`_ in the *ElastiCache User Guide* .

 

.. note::

   

  This operation is valid for Redis only.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/CreateReplicationGroup>`_


========
Synopsis
========

::

    create-replication-group
  --replication-group-id <value>
  --replication-group-description <value>
  [--primary-cluster-id <value>]
  [--automatic-failover-enabled | --no-automatic-failover-enabled]
  [--num-cache-clusters <value>]
  [--preferred-cache-cluster-a-zs <value>]
  [--num-node-groups <value>]
  [--replicas-per-node-group <value>]
  [--node-group-configuration <value>]
  [--cache-node-type <value>]
  [--engine <value>]
  [--engine-version <value>]
  [--cache-parameter-group-name <value>]
  [--cache-subnet-group-name <value>]
  [--cache-security-group-names <value>]
  [--security-group-ids <value>]
  [--tags <value>]
  [--snapshot-arns <value>]
  [--snapshot-name <value>]
  [--preferred-maintenance-window <value>]
  [--port <value>]
  [--notification-topic-arn <value>]
  [--auto-minor-version-upgrade | --no-auto-minor-version-upgrade]
  [--snapshot-retention-limit <value>]
  [--snapshot-window <value>]
  [--auth-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--replication-group-id`` (string)


  The replication group identifier. This parameter is stored as a lowercase string.

   

  Constraints:

   

   
  * A name must contain from 1 to 20 alphanumeric characters or hyphens. 
   
  * The first character must be a letter. 
   
  * A name cannot end with a hyphen or contain two consecutive hyphens. 
   

  

``--replication-group-description`` (string)


  A user-created description for the replication group.

  

``--primary-cluster-id`` (string)


  The identifier of the cache cluster that serves as the primary for this replication group. This cache cluster must already exist and have a status of ``available`` .

   

  This parameter is not required if ``NumCacheClusters`` , ``NumNodeGroups`` , or ``ReplicasPerNodeGroup`` is specified.

  

``--automatic-failover-enabled`` | ``--no-automatic-failover-enabled`` (boolean)


  Specifies whether a read-only replica is automatically promoted to read/write primary if the existing primary fails.

   

  If ``true`` , Multi-AZ is enabled for this replication group. If ``false`` , Multi-AZ is disabled for this replication group.

   

   ``AutomaticFailoverEnabled`` must be enabled for Redis (cluster mode enabled) replication groups.

   

  Default: false

   

  .. note::

     

    ElastiCache Multi-AZ replication groups is not supported on:

     

     
    * Redis versions earlier than 2.8.6. 
     
    * Redis (cluster mode disabled): T1 and T2 node types. Redis (cluster mode enabled): T2 node types. 
     

     

  

``--num-cache-clusters`` (integer)


  The number of clusters this replication group initially has.

   

  This parameter is not used if there is more than one node group (shard). You should use ``ReplicasPerNodeGroup`` instead.

   

  If ``AutomaticFailoverEnabled`` is ``true`` , the value of this parameter must be at least 2. If ``AutomaticFailoverEnabled`` is ``false`` you can omit this parameter (it will default to 1), or you can explicitly set it to a value between 2 and 6.

   

  The maximum permitted value for ``NumCacheClusters`` is 6 (primary plus 5 replicas).

  

``--preferred-cache-cluster-a-zs`` (list)


  A list of EC2 Availability Zones in which the replication group's cache clusters are created. The order of the Availability Zones in the list is the order in which clusters are allocated. The primary cluster is created in the first AZ in the list.

   

  This parameter is not used if there is more than one node group (shard). You should use ``NodeGroupConfiguration`` instead.

   

  .. note::

     

    If you are creating your replication group in an Amazon VPC (recommended), you can only locate cache clusters in Availability Zones associated with the subnets in the selected subnet group.

     

    The number of Availability Zones listed must equal the value of ``NumCacheClusters`` .

     

   

  Default: system chosen Availability Zones.

  



Syntax::

  "string" "string" ...



``--num-node-groups`` (integer)


  An optional parameter that specifies the number of node groups (shards) for this Redis (cluster mode enabled) replication group. For Redis (cluster mode disabled) either omit this parameter or set it to 1.

   

  Default: 1

  

``--replicas-per-node-group`` (integer)


  An optional parameter that specifies the number of replica nodes in each node group (shard). Valid values are 0 to 5.

  

``--node-group-configuration`` (list)


  A list of node group (shard) configuration options. Each node group (shard) configuration has the following: Slots, PrimaryAvailabilityZone, ReplicaAvailabilityZones, ReplicaCount.

   

  If you're creating a Redis (cluster mode disabled) or a Redis (cluster mode enabled) replication group, you can use this parameter to individually configure each node group (shard), or you can omit this parameter.

  



Shorthand Syntax::

    Slots=string,ReplicaCount=integer,PrimaryAvailabilityZone=string,ReplicaAvailabilityZones=string,string ...




JSON Syntax::

  [
    {
      "Slots": "string",
      "ReplicaCount": integer,
      "PrimaryAvailabilityZone": "string",
      "ReplicaAvailabilityZones": ["string", ...]
    }
    ...
  ]



``--cache-node-type`` (string)


  The compute and memory capacity of the nodes in the node group (shard).

   

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

  

``--engine`` (string)


  The name of the cache engine to be used for the cache clusters in this replication group.

  

``--engine-version`` (string)


  The version number of the cache engine to be used for the cache clusters in this replication group. To view the supported cache engine versions, use the ``describe-cache-engine-versions`` operation.

   

   **Important:** You can upgrade to a newer engine version (see `Selecting a Cache Engine and Version <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/SelectEngine.html#VersionManagement>`_ ) in the *ElastiCache User Guide* , but you cannot downgrade to an earlier engine version. If you want to use an earlier engine version, you must delete the existing cache cluster or replication group and create it anew with the earlier engine version. 

  

``--cache-parameter-group-name`` (string)


  The name of the parameter group to associate with this replication group. If this argument is omitted, the default cache parameter group for the specified engine is used.

   

  If you are running Redis version 3.2.4 or later, only one node group (shard), and want to use a default parameter group, we recommend that you specify the parameter group by name. 

   

   
  * To create a Redis (cluster mode disabled) replication group, use ``CacheParameterGroupName=default.redis3.2`` . 
   
  * To create a Redis (cluster mode enabled) replication group, use ``CacheParameterGroupName=default.redis3.2.cluster.on`` . 
   

  

``--cache-subnet-group-name`` (string)


  The name of the cache subnet group to be used for the replication group.

   

  .. warning::

     

    If you're going to launch your cluster in an Amazon VPC, you need to create a subnet group before you start creating a cluster. For more information, see `Subnets and Subnet Groups <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/SubnetGroups.html>`_ .

     

  

``--cache-security-group-names`` (list)


  A list of cache security group names to associate with this replication group.

  



Syntax::

  "string" "string" ...



``--security-group-ids`` (list)


  One or more Amazon VPC security groups associated with this replication group.

   

  Use this parameter only when you are creating a replication group in an Amazon Virtual Private Cloud (Amazon VPC).

  



Syntax::

  "string" "string" ...



``--tags`` (list)


  A list of cost allocation tags to be added to this resource. A tag is a key-value pair. A tag key must be accompanied by a tag value.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--snapshot-arns`` (list)


  A list of Amazon Resource Names (ARN) that uniquely identify the Redis RDB snapshot files stored in Amazon S3. The snapshot files are used to populate the new replication group. The Amazon S3 object name in the ARN cannot contain any commas. The new replication group will have the number of node groups (console: shards) specified by the parameter *NumNodeGroups* or the number of node groups configured by *NodeGroupConfiguration* regardless of the number of ARNs specified here.

   

  .. note::

     

    This parameter is only valid if the ``Engine`` parameter is ``redis`` .

     

   

  Example of an Amazon S3 ARN: ``arn:aws:s3:::my_bucket/snapshot1.rdb``  

  



Syntax::

  "string" "string" ...



``--snapshot-name`` (string)


  The name of a snapshot from which to restore data into the new replication group. The snapshot status changes to ``restoring`` while the new replication group is being created.

   

  .. note::

     

    This parameter is only valid if the ``Engine`` parameter is ``redis`` .

     

  

``--preferred-maintenance-window`` (string)


  Specifies the weekly time range during which maintenance on the cache cluster is performed. It is specified as a range in the format ddd:hh24:mi-ddd:hh24:mi (24H Clock UTC). The minimum maintenance window is a 60 minute period. Valid values for ``ddd`` are:

   

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

  

``--port`` (integer)


  The port number on which each member of the replication group accepts connections.

  

``--notification-topic-arn`` (string)


  The Amazon Resource Name (ARN) of the Amazon Simple Notification Service (SNS) topic to which notifications are sent.

   

  .. note::

     

    The Amazon SNS topic owner must be the same as the cache cluster owner.

     

  

``--auto-minor-version-upgrade`` | ``--no-auto-minor-version-upgrade`` (boolean)


  This parameter is currently disabled.

  

``--snapshot-retention-limit`` (integer)


  The number of days for which ElastiCache retains automatic snapshots before deleting them. For example, if you set ``SnapshotRetentionLimit`` to 5, a snapshot that was taken today is retained for 5 days before being deleted.

   

  .. note::

     

    This parameter is only valid if the ``Engine`` parameter is ``redis`` .

     

   

  Default: 0 (i.e., automatic backups are disabled for this cache cluster).

  

``--snapshot-window`` (string)


  The daily time range (in UTC) during which ElastiCache begins taking a daily snapshot of your node group (shard).

   

  Example: ``05:00-09:00``  

   

  If you do not specify this parameter, ElastiCache automatically chooses an appropriate time range.

   

  .. note::

     

    This parameter is only valid if the ``Engine`` parameter is ``redis`` .

     

  

``--auth-token`` (string)


   **Reserved parameter.** The password used to access a password protected server.

   

  Password constraints:

   

   
  * Must be only printable ASCII characters. 
   
  * Must be at least 16 characters and no more than 128 characters in length. 
   
  * Cannot contain any of the following characters: '/', '"', or "@".  
   

   

  For more information, see `AUTH password <http://redis.io/commands/AUTH>`_ at Redis.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create an Amazon ElastiCache Replication Group**

The following ``create-replication-group`` command launches a new Amazon ElastiCache Redis replication group::

    aws elasticache create-replication-group --replication-group-id myRedis \
    --replication-group-description "desc of myRedis" \
    --automatic-failover-enabled --num-cache-clusters 3 \
    --cache-node-type cache.m3.medium \
    --engine redis --engine-version 2.8.24 \
    --cache-parameter-group-name default.redis2.8 \
    --cache-subnet-group-name default --security-group-ids sg-12345678 

In the preceding example, the replication group is created with 3 clusters(primary plus 2 replicas) and has a cache node class of cach3.m3.medium.
With `--automatic-failover-enabled` option, Multi-AZ and automatic failover are enabled.
    
This command output a JSON block that indicates that the replication group was created.


======
Output
======

ReplicationGroup -> (structure)

  

  Contains all of the attributes of a specific Redis replication group.

  

  ReplicationGroupId -> (string)

    

    The identifier for the replication group.

    

    

  Description -> (string)

    

    The description of the replication group.

    

    

  Status -> (string)

    

    The current state of this replication group - ``creating`` , ``available`` , ``modifying`` , ``deleting`` , ``create-failed`` , ``snapshotting`` .

    

    

  PendingModifiedValues -> (structure)

    

    A group of settings to be applied to the replication group, either immediately or during the next maintenance window.

    

    PrimaryClusterId -> (string)

      

      The primary cluster ID that is applied immediately (if ``--apply-immediately`` was specified), or during the next maintenance window.

      

      

    AutomaticFailoverStatus -> (string)

      

      Indicates the status of Multi-AZ for this Redis replication group.

       

      .. note::

         

        ElastiCache Multi-AZ replication groups are not supported on:

         

         
        * Redis versions earlier than 2.8.6. 
         
        * Redis (cluster mode disabled):T1 and T2 cache node types. Redis (cluster mode enabled): T1 node types. 
         

         

      

      

    

  MemberClusters -> (list)

    

    The names of all the cache clusters that are part of this replication group.

    

    (string)

      

      

    

  NodeGroups -> (list)

    

    A single element list with information about the nodes in the replication group.

    

    (structure)

      

      Represents a collection of cache nodes in a replication group. One node in the node group is the read/write primary node. All the other nodes are read-only Replica nodes.

      

      NodeGroupId -> (string)

        

        The identifier for the node group (shard). A Redis (cluster mode disabled) replication group contains only 1 node group; therefore, the node group ID is 0001. A Redis (cluster mode enabled) replication group contains 1 to 15 node groups numbered 0001 to 0015. 

        

        

      Status -> (string)

        

        The current state of this replication group - ``creating`` , ``available`` , etc.

        

        

      PrimaryEndpoint -> (structure)

        

        The endpoint of the primary node in this node group (shard).

        

        Address -> (string)

          

          The DNS hostname of the cache node.

          

          

        Port -> (integer)

          

          The port number that the cache engine is listening on.

          

          

        

      Slots -> (string)

        

        The keyspace for this node group (shard).

        

        

      NodeGroupMembers -> (list)

        

        A list containing information about individual nodes within the node group (shard).

        

        (structure)

          

          Represents a single node within a node group (shard).

          

          CacheClusterId -> (string)

            

            The ID of the cache cluster to which the node belongs.

            

            

          CacheNodeId -> (string)

            

            The ID of the node within its cache cluster. A node ID is a numeric identifier (0001, 0002, etc.).

            

            

          ReadEndpoint -> (structure)

            

            Represents the information required for client programs to connect to a cache node.

            

            Address -> (string)

              

              The DNS hostname of the cache node.

              

              

            Port -> (integer)

              

              The port number that the cache engine is listening on.

              

              

            

          PreferredAvailabilityZone -> (string)

            

            The name of the Availability Zone in which the node is located.

            

            

          CurrentRole -> (string)

            

            The role that is currently assigned to the node - ``primary`` or ``replica`` .

            

            

          

        

      

    

  SnapshottingClusterId -> (string)

    

    The cache cluster ID that is used as the daily snapshot source for the replication group.

    

    

  AutomaticFailover -> (string)

    

    Indicates the status of Multi-AZ for this replication group.

     

    .. note::

       

      ElastiCache Multi-AZ replication groups are not supported on:

       

       
      * Redis versions earlier than 2.8.6. 
       
      * Redis (cluster mode disabled):T1 and T2 cache node types. Redis (cluster mode enabled): T1 node types. 
       

       

    

    

  ConfigurationEndpoint -> (structure)

    

    The configuration endpoint for this replicaiton group. Use the configuration endpoint to connect to this replication group.

    

    Address -> (string)

      

      The DNS hostname of the cache node.

      

      

    Port -> (integer)

      

      The port number that the cache engine is listening on.

      

      

    

  SnapshotRetentionLimit -> (integer)

    

    The number of days for which ElastiCache retains automatic cache cluster snapshots before deleting them. For example, if you set ``SnapshotRetentionLimit`` to 5, a snapshot that was taken today is retained for 5 days before being deleted.

     

    .. warning::

       

      If the value of ``SnapshotRetentionLimit`` is set to zero (0), backups are turned off.

       

    

    

  SnapshotWindow -> (string)

    

    The daily time range (in UTC) during which ElastiCache begins taking a daily snapshot of your node group (shard).

     

    Example: ``05:00-09:00``  

     

    If you do not specify this parameter, ElastiCache automatically chooses an appropriate time range.

     

     **Note:** This parameter is only valid if the ``Engine`` parameter is ``redis`` .

    

    

  ClusterEnabled -> (boolean)

    

    A flag indicating whether or not this replication group is cluster enabled; i.e., whether its data can be partitioned across multiple shards (API/CLI: node groups).

     

    Valid values: ``true`` | ``false``  

    

    

  CacheNodeType -> (string)

    

    The name of the compute and memory capacity node type for each node in the replication group.

    

    

  

