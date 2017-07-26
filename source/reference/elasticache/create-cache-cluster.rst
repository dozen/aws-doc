[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache create-cache-cluster:


********************
create-cache-cluster
********************



===========
Description
===========



The *create-cache-cluster* action creates a cache cluster. All nodes in the cache cluster run the same protocol-compliant cache engine software, either Memcached or Redis.



========
Synopsis
========

::

    create-cache-cluster
  --cache-cluster-id <value>
  [--replication-group-id <value>]
  [--az-mode <value>]
  [--preferred-availability-zone <value>]
  [--preferred-availability-zones <value>]
  [--num-cache-nodes <value>]
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
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cache-cluster-id`` (string)


  The node group identifier. This parameter is stored as a lowercase string.

   

  Constraints:

   

   
  * A name must contain from 1 to 20 alphanumeric characters or hyphens.
   
  * The first character must be a letter.
   
  * A name cannot end with a hyphen or contain two consecutive hyphens.
   

  

``--replication-group-id`` (string)


  The ID of the replication group to which this cache cluster should belong. If this parameter is specified, the cache cluster will be added to the specified replication group as a read replica; otherwise, the cache cluster will be a standalone primary that is not part of any replication group.

   

  If the specified replication group is Multi-AZ enabled and the availability zone is not specified, the cache cluster will be created in availability zones that provide the best spread of read replicas across availability zones.

   

  **Note:** This parameter is only valid if the ``Engine`` parameter is ``redis`` .

  

``--az-mode`` (string)


  Specifies whether the nodes in this Memcached node group are created in a single Availability Zone or created across multiple Availability Zones in the cluster's region.

   

  This parameter is only supported for Memcached cache clusters.

   

  If the ``az-mode`` and ``PreferredAvailabilityZones`` are not specified, ElastiCache assumes ``single-az`` mode.

  

  Possible values:

  
  *   ``single-az``

  
  *   ``cross-az``

  

  

``--preferred-availability-zone`` (string)


  The EC2 Availability Zone in which the cache cluster will be created.

   

  All nodes belonging to this Memcached cache cluster are placed in the preferred Availability Zone. If you want to create your nodes across multiple Availability Zones, use ``PreferredAvailabilityZones`` .

   

  Default: System chosen Availability Zone.

  

``--preferred-availability-zones`` (list)


  A list of the Availability Zones in which cache nodes will be created. The order of the zones in the list is not important.

   

  This option is only supported on Memcached.

   

  .. note::

     

    If you are creating your cache cluster in an Amazon VPC (recommended) you can only locate nodes in Availability Zones that are associated with the subnets in the selected subnet group.

     

    The number of Availability Zones listed must equal the value of ``NumCacheNodes`` .

     

   

  If you want all the nodes in the same Availability Zone, use ``PreferredAvailabilityZone`` instead, or repeat the Availability Zone multiple times in the list.

   

  Default: System chosen Availability Zones.

   

  Example: One Memcached node in each of three different Availability Zones: ``PreferredAvailabilityZones.member.1=us-west-2aPreferredAvailabilityZones.member.2=us-west-2bPreferredAvailabilityZones.member.3=us-west-2c`` 

   

  Example: All three Memcached nodes in one Availability Zone: ``PreferredAvailabilityZones.member.1=us-west-2aPreferredAvailabilityZones.member.2=us-west-2aPreferredAvailabilityZones.member.3=us-west-2a`` 

  



Syntax::

  "string" "string" ...



``--num-cache-nodes`` (integer)


  The initial number of cache nodes that the cache cluster will have.

   

  For clusters running Redis, this value must be 1. For clusters running Memcached, this value must be between 1 and 20.

   

  If you need more than 20 nodes for your Memcached cluster, please fill out the ElastiCache Limit Increase Request form at `http\://aws.amazon.com/contact-us/elasticache-node-limit-request/`_ .

  

``--cache-node-type`` (string)


  The compute and memory capacity of the nodes in the node group.

   

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

  

``--engine`` (string)


  The name of the cache engine to be used for this cache cluster.

   

  Valid values for this parameter are:

   

  ``memcached`` | ``redis`` 

  

``--engine-version`` (string)


  The version number of the cache engine to be used for this cache cluster. To view the supported cache engine versions, use the *describe-cache-engine-versions* action.

  

``--cache-parameter-group-name`` (string)


  The name of the parameter group to associate with this cache cluster. If this argument is omitted, the default parameter group for the specified engine is used.

  

``--cache-subnet-group-name`` (string)


  The name of the subnet group to be used for the cache cluster.

   

  Use this parameter only when you are creating a cache cluster in an Amazon Virtual Private Cloud (VPC).

  

``--cache-security-group-names`` (list)


  A list of security group names to associate with this cache cluster.

   

  Use this parameter only when you are creating a cache cluster outside of an Amazon Virtual Private Cloud (VPC).

  



Syntax::

  "string" "string" ...



``--security-group-ids`` (list)


  One or more VPC security groups associated with the cache cluster.

   

  Use this parameter only when you are creating a cache cluster in an Amazon Virtual Private Cloud (VPC).

  



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


  A single-element string list containing an Amazon Resource Name (ARN) that uniquely identifies a Redis RDB snapshot file stored in Amazon S3. The snapshot file will be used to populate the node group. The Amazon S3 object name in the ARN cannot contain any commas.

   

  **Note:** This parameter is only valid if the ``Engine`` parameter is ``redis`` .

   

  Example of an Amazon S3 ARN: ``arn:aws:s3:::my_bucket/snapshot1.rdb`` 

  



Syntax::

  "string" "string" ...



``--snapshot-name`` (string)


  The name of a snapshot from which to restore data into the new node group. The snapshot status changes to ``restoring`` while the new node group is being created.

   

  **Note:** This parameter is only valid if the ``Engine`` parameter is ``redis`` .

  

``--preferred-maintenance-window`` (string)


  Specifies the weekly time range during which maintenance on the cache cluster is performed. It is specified as a range in the format ddd:hh24:mi-ddd:hh24:mi (24H Clock UTC). The minimum maintenance window is a 60 minute period. Valid values for ``ddd`` are:

   

   
  * ``sun`` 
   
  * ``mon`` 
   
  * ``tue`` 
   
  * ``wed`` 
   
  * ``thu`` 
   
  * ``fri`` 
   
  * ``sat`` 
   

   

  Example: ``sun:05:00-sun:09:00`` 

  

``--port`` (integer)


  The port number on which each of the cache nodes will accept connections.

  

``--notification-topic-arn`` (string)


  The Amazon Resource Name (ARN) of the Amazon Simple Notification Service (SNS) topic to which notifications will be sent.

   

  .. note::

    The Amazon SNS topic owner must be the same as the cache cluster owner.

  

``--auto-minor-version-upgrade`` | ``--no-auto-minor-version-upgrade`` (boolean)


  This parameter is currently disabled.

  

``--snapshot-retention-limit`` (integer)


  The number of days for which ElastiCache will retain automatic snapshots before deleting them. For example, if you set ``SnapshotRetentionLimit`` to 5, then a snapshot that was taken today will be retained for 5 days before being deleted.

   

  **Note:** This parameter is only valid if the ``Engine`` parameter is ``redis`` .

   

  Default: 0 (i.e., automatic backups are disabled for this cache cluster).

  

``--snapshot-window`` (string)


  The daily time range (in UTC) during which ElastiCache will begin taking a daily snapshot of your node group.

   

  Example: ``05:00-09:00`` 

   

  If you do not specify this parameter, then ElastiCache will automatically choose an appropriate time range.

   

  **Note:** This parameter is only valid if the ``Engine`` parameter is ``redis`` .

  

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
.. _Cache Node Type-Specific Parameters for Redis: http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheParameterGroups.Redis.html#CacheParameterGroups.Redis.NodeSpecific
.. _Amazon ElastiCache Product Features and Details: http://aws.amazon.com/elasticache/details
.. _http\://aws.amazon.com/contact-us/elasticache-node-limit-request/: http://aws.amazon.com/contact-us/elasticache-node-limit-request/
