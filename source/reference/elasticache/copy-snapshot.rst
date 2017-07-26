[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache copy-snapshot:


*************
copy-snapshot
*************



===========
Description
===========



The *copy-snapshot* action makes a copy of an existing snapshot.



========
Synopsis
========

::

    copy-snapshot
  --source-snapshot-name <value>
  --target-snapshot-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--source-snapshot-name`` (string)


  The name of an existing snapshot from which to copy.

  

``--target-snapshot-name`` (string)


  A name for the copied snapshot.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Snapshot -> (structure)

  

  Represents a copy of an entire cache cluster as of the time when the snapshot was taken.

  

  SnapshotName -> (string)

    

    The name of a snapshot. For an automatic snapshot, the name is system-generated; for a manual snapshot, this is the user-provided name.

    

    

  CacheClusterId -> (string)

    

    The user-supplied identifier of the source cache cluster.

    

    

  SnapshotStatus -> (string)

    

    The status of the snapshot. Valid values: ``creating`` | ``available`` | ``restoring`` | ``copying`` | ``deleting`` .

    

    

  SnapshotSource -> (string)

    

    Indicates whether the snapshot is from an automatic backup (``automated`` ) or was created manually (``manual`` ).

    

    

  CacheNodeType -> (string)

    

    The name of the compute and memory capacity node type for the source cache cluster.

     

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

    

    The name of the cache engine (*memcached* or *redis* ) used by the source cache cluster.

    

    

  EngineVersion -> (string)

    

    The version of the cache engine version that is used by the source cache cluster.

    

    

  NumCacheNodes -> (integer)

    

    The number of cache nodes in the source cache cluster.

     

    For clusters running Redis, this value must be 1. For clusters running Memcached, this value must be between 1 and 20.

    

    

  PreferredAvailabilityZone -> (string)

    

    The name of the Availability Zone in which the source cache cluster is located.

    

    

  CacheClusterCreateTime -> (timestamp)

    

    The date and time when the source cache cluster was created.

    

    

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

    

    

  TopicArn -> (string)

    

    The Amazon Resource Name (ARN) for the topic used by the source cache cluster for publishing notifications.

    

    

  Port -> (integer)

    

    The port number used by each cache nodes in the source cache cluster.

    

    

  CacheParameterGroupName -> (string)

    

    The cache parameter group that is associated with the source cache cluster.

    

    

  CacheSubnetGroupName -> (string)

    

    The name of the cache subnet group associated with the source cache cluster.

    

    

  VpcId -> (string)

    

    The Amazon Virtual Private Cloud identifier (VPC ID) of the cache subnet group for the source cache cluster.

    

    

  AutoMinorVersionUpgrade -> (boolean)

    

    This parameter is currently disabled.

    

    

  SnapshotRetentionLimit -> (integer)

    

    For an automatic snapshot, the number of days for which ElastiCache will retain the snapshot before deleting it.

     

    For manual snapshots, this field reflects the *SnapshotRetentionLimit* for the source cache cluster when the snapshot was created. This field is otherwise ignored: Manual snapshots do not expire, and can only be deleted using the *delete-snapshot* action. 

     

    **Important** If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.

    

    

  SnapshotWindow -> (string)

    

    The daily time range during which ElastiCache takes daily snapshots of the source cache cluster.

    

    

  NodeSnapshots -> (list)

    

    A list of the cache nodes in the source cache cluster.

    

    (structure)

      

      Represents an individual cache node in a snapshot of a cache cluster.

      

      CacheNodeId -> (string)

        

        The cache node identifier for the node in the source cache cluster.

        

        

      CacheSize -> (string)

        

        The size of the cache on the source cache node.

        

        

      CacheNodeCreateTime -> (timestamp)

        

        The date and time when the cache node was created in the source cache cluster.

        

        

      SnapshotCreateTime -> (timestamp)

        

        The date and time when the source node's metadata and cache data set was obtained for the snapshot.

        

        

      

    

  



.. _Cache Node Type-Specific Parameters for Memcached: http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheParameterGroups.Memcached.html#CacheParameterGroups.Memcached.NodeSpecific
.. _Amazon ElastiCache Product Features and Details: http://aws.amazon.com/elasticache/details
.. _Cache Node Type-Specific Parameters for Redis: http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheParameterGroups.Redis.html#CacheParameterGroups.Redis.NodeSpecific
