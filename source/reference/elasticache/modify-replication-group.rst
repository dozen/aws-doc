[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache modify-replication-group:


************************
modify-replication-group
************************



===========
Description
===========



Modifies the settings for a replication group.

 

.. warning::

   

  Due to current limitations on Redis (cluster mode disabled), this operation or parameter is not supported on Redis (cluster mode enabled) replication groups.

   

 

.. note::

   

  This operation is valid for Redis only.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/ModifyReplicationGroup>`_


========
Synopsis
========

::

    modify-replication-group
  --replication-group-id <value>
  [--replication-group-description <value>]
  [--primary-cluster-id <value>]
  [--snapshotting-cluster-id <value>]
  [--automatic-failover-enabled | --no-automatic-failover-enabled]
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
  [--node-group-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--replication-group-id`` (string)


  The identifier of the replication group to modify.

  

``--replication-group-description`` (string)


  A description for the replication group. Maximum length is 255 characters.

  

``--primary-cluster-id`` (string)


  For replication groups with a single primary, if this parameter is specified, ElastiCache promotes the specified cluster in the specified replication group to the primary role. The nodes of all other clusters in the replication group are read replicas.

  

``--snapshotting-cluster-id`` (string)


  The cache cluster ID that is used as the daily snapshot source for the replication group. This parameter cannot be set for Redis (cluster mode enabled) replication groups.

  

``--automatic-failover-enabled`` | ``--no-automatic-failover-enabled`` (boolean)


  Determines whether a read replica is automatically promoted to read/write primary if the existing primary encounters a failure.

   

  Valid values: ``true`` | ``false``  

   

  .. note::

     

    ElastiCache Multi-AZ replication groups are not supported on:

     

     
    * Redis versions earlier than 2.8.6. 
     
    * Redis (cluster mode disabled):T1 and T2 cache node types. Redis (cluster mode enabled): T1 node types. 
     

     

  

``--cache-security-group-names`` (list)


  A list of cache security group names to authorize for the clusters in this replication group. This change is asynchronously applied as soon as possible.

   

  This parameter can be used only with replication group containing cache clusters running outside of an Amazon Virtual Private Cloud (Amazon VPC).

   

  Constraints: Must contain no more than 255 alphanumeric characters. Must not be ``Default`` .

  



Syntax::

  "string" "string" ...



``--security-group-ids`` (list)


  Specifies the VPC Security Groups associated with the cache clusters in the replication group.

   

  This parameter can be used only with replication group containing cache clusters running in an Amazon Virtual Private Cloud (Amazon VPC).

  



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

     

    The Amazon SNS topic owner must be same as the replication group owner. 

     

  

``--cache-parameter-group-name`` (string)


  The name of the cache parameter group to apply to all of the clusters in this replication group. This change is asynchronously applied as soon as possible for parameters when the ``ApplyImmediately`` parameter is specified as ``true`` for this request.

  

``--notification-topic-status`` (string)


  The status of the Amazon SNS notification topic for the replication group. Notifications are sent only if the status is ``active`` .

   

  Valid values: ``active`` | ``inactive``  

  

``--apply-immediately`` | ``--no-apply-immediately`` (boolean)


  If ``true`` , this parameter causes the modifications in this request and any pending modifications to be applied, asynchronously and as soon as possible, regardless of the ``PreferredMaintenanceWindow`` setting for the replication group.

   

  If ``false`` , changes to the nodes in the replication group are applied on the next maintenance reboot, or the next failure reboot, whichever occurs first.

   

  Valid values: ``true`` | ``false``  

   

  Default: ``false``  

  

``--engine-version`` (string)


  The upgraded version of the cache engine to be run on the cache clusters in the replication group.

   

   **Important:** You can upgrade to a newer engine version (see `Selecting a Cache Engine and Version <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/SelectEngine.html#VersionManagement>`_ ), but you cannot downgrade to an earlier engine version. If you want to use an earlier engine version, you must delete the existing replication group and create it anew with the earlier engine version. 

  

``--auto-minor-version-upgrade`` | ``--no-auto-minor-version-upgrade`` (boolean)


  This parameter is currently disabled.

  

``--snapshot-retention-limit`` (integer)


  The number of days for which ElastiCache retains automatic node group (shard) snapshots before deleting them. For example, if you set ``SnapshotRetentionLimit`` to 5, a snapshot that was taken today is retained for 5 days before being deleted.

   

   **Important** If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.

  

``--snapshot-window`` (string)


  The daily time range (in UTC) during which ElastiCache begins taking a daily snapshot of the node group (shard) specified by ``SnapshottingClusterId`` .

   

  Example: ``05:00-09:00``  

   

  If you do not specify this parameter, ElastiCache automatically chooses an appropriate time range.

  

``--cache-node-type`` (string)


  A valid cache node type that you want to scale this replication group to.

  

``--node-group-id`` (string)


  The name of the Node Group (called shard in the console).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To promote a cache cluster to the primary role**

This example promotes the cache cluster *mycluster-002* to the primary role for the specified replication group.

Command::

  aws elasticache modify-replication-group --replication-group-id mycluster \
  --primary-cluster-id mycluster-002 --apply-immediately

The nodes of all other cache clusters in the replication group will be read replicas.
If the specified group's *autofailover* is enabled, you cannot mannualy promote cache clusters.


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

    

    

  

