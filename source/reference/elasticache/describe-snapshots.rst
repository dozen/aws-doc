[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache describe-snapshots:


******************
describe-snapshots
******************



===========
Description
===========



The *describe-snapshots* action returns information about cache cluster snapshots. By default, *describe-snapshots* lists all of your snapshots; it can optionally describe a single snapshot, or just the snapshots associated with a particular cache cluster.



``describe-snapshots`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Snapshots``


========
Synopsis
========

::

    describe-snapshots
  [--cache-cluster-id <value>]
  [--snapshot-name <value>]
  [--snapshot-source <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cache-cluster-id`` (string)


  A user-supplied cluster identifier. If this parameter is specified, only snapshots associated with that specific cache cluster will be described.

  

``--snapshot-name`` (string)


  A user-supplied name of the snapshot. If this parameter is specified, only this snapshot will be described.

  

``--snapshot-source`` (string)


  If set to ``system`` , the output shows snapshots that were automatically created by ElastiCache. If set to ``user`` the output shows snapshots that were manually created. If omitted, the output shows both automatically and manually created snapshots.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Marker -> (string)

  

  An optional marker returned from a prior request. Use this marker for pagination of results from this action. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by *MaxRecords* .

  

  

Snapshots -> (list)

  

  A list of snapshots. Each item in the list contains detailed information about one snapshot.

  

  (structure)

    

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
