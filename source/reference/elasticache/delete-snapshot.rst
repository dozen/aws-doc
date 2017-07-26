[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache delete-snapshot:


***************
delete-snapshot
***************



===========
Description
===========



Deletes an existing snapshot. When you receive a successful response from this operation, ElastiCache immediately begins deleting the snapshot; you cannot cancel or revert this operation.

 

.. note::

   

  This operation is valid for Redis only.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/DeleteSnapshot>`_


========
Synopsis
========

::

    delete-snapshot
  --snapshot-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--snapshot-name`` (string)


  The name of the snapshot to be deleted.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Snapshot -> (structure)

  

  Represents a copy of an entire Redis cache cluster as of the time when the snapshot was taken.

  

  SnapshotName -> (string)

    

    The name of a snapshot. For an automatic snapshot, the name is system-generated. For a manual snapshot, this is the user-provided name.

    

    

  ReplicationGroupId -> (string)

    

    The unique identifier of the source replication group.

    

    

  ReplicationGroupDescription -> (string)

    

    A description of the source replication group.

    

    

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

    

    The name of the cache engine (``memcached`` or ``redis`` ) used by the source cache cluster.

    

    

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

    

    For an automatic snapshot, the number of days for which ElastiCache retains the snapshot before deleting it.

     

    For manual snapshots, this field reflects the ``SnapshotRetentionLimit`` for the source cache cluster when the snapshot was created. This field is otherwise ignored: Manual snapshots do not expire, and can only be deleted using the ``delete-snapshot`` operation. 

     

     **Important** If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.

    

    

  SnapshotWindow -> (string)

    

    The daily time range during which ElastiCache takes daily snapshots of the source cache cluster.

    

    

  NumNodeGroups -> (integer)

    

    The number of node groups (shards) in this snapshot. When restoring from a snapshot, the number of node groups (shards) in the snapshot and in the restored replication group must be the same.

    

    

  AutomaticFailover -> (string)

    

    Indicates the status of Multi-AZ for the source replication group.

     

    .. note::

       

      ElastiCache Multi-AZ replication groups are not supported on:

       

       
      * Redis versions earlier than 2.8.6. 
       
      * Redis (cluster mode disabled):T1 and T2 cache node types. Redis (cluster mode enabled): T1 node types. 
       

       

    

    

  NodeSnapshots -> (list)

    

    A list of the cache nodes in the source cache cluster.

    

    (structure)

      

      Represents an individual cache node in a snapshot of a cache cluster.

      

      CacheClusterId -> (string)

        

        A unique identifier for the source cache cluster.

        

        

      NodeGroupId -> (string)

        

        A unique identifier for the source node group (shard).

        

        

      CacheNodeId -> (string)

        

        The cache node identifier for the node in the source cache cluster.

        

        

      NodeGroupConfiguration -> (structure)

        

        The configuration for the source node group (shard).

        

        Slots -> (string)

          

          A string that specifies the keyspace for a particular node group. Keyspaces range from 0 to 16,383. The string is in the format ``startkey-endkey`` .

           

          Example: ``"0-3999"``  

          

          

        ReplicaCount -> (integer)

          

          The number of read replica nodes in this node group (shard).

          

          

        PrimaryAvailabilityZone -> (string)

          

          The Availability Zone where the primary node of this node group (shard) is launched.

          

          

        ReplicaAvailabilityZones -> (list)

          

          A list of Availability Zones to be used for the read replicas. The number of Availability Zones in this list must match the value of ``ReplicaCount`` or ``ReplicasPerNodeGroup`` if not specified.

          

          (string)

            

            

          

        

      CacheSize -> (string)

        

        The size of the cache on the source cache node.

        

        

      CacheNodeCreateTime -> (timestamp)

        

        The date and time when the cache node was created in the source cache cluster.

        

        

      SnapshotCreateTime -> (timestamp)

        

        The date and time when the source node's metadata and cache data set was obtained for the snapshot.

        

        

      

    

  

