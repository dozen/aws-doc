[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache delete-replication-group:


************************
delete-replication-group
************************



===========
Description
===========



Deletes an existing replication group. By default, this operation deletes the entire replication group, including the primary/primaries and all of the read replicas. If the replication group has only one primary, you can optionally delete only the read replicas, while retaining the primary by setting ``RetainPrimaryCluster=true`` .

 

When you receive a successful response from this operation, Amazon ElastiCache immediately begins deleting the selected resources; you cannot cancel or revert this operation.

 

.. note::

   

  This operation is valid for Redis only.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/DeleteReplicationGroup>`_


========
Synopsis
========

::

    delete-replication-group
  --replication-group-id <value>
  [--retain-primary-cluster | --no-retain-primary-cluster]
  [--final-snapshot-identifier <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--replication-group-id`` (string)


  The identifier for the cluster to be deleted. This parameter is not case sensitive.

  

``--retain-primary-cluster`` | ``--no-retain-primary-cluster`` (boolean)


  If set to ``true`` , all of the read replicas are deleted, but the primary node is retained.

  

``--final-snapshot-identifier`` (string)


  The name of a final node group (shard) snapshot. ElastiCache creates the snapshot from the primary node in the cluster, rather than one of the replicas; this is to ensure that it captures the freshest data. After the final snapshot is taken, the replication group is immediately deleted.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    

  

