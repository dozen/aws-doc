[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache test-failover:


*************
test-failover
*************



===========
Description
===========



Represents the input of a ``test-failover`` operation which test automatic failover on a specified node group (called shard in the console) in a replication group (called cluster in the console).

 

 **Note the following**  

 

 
* A customer can use this operation to test automatic failover on up to 5 shards (called node groups in the ElastiCache API and AWS CLI) in any rolling 24-hour period. 
 
* If calling this operation on shards in different clusters (called replication groups in the API and CLI), the calls can be made concurrently.   
 
* If calling this operation multiple times on different shards in the same Redis (cluster mode enabled) replication group, the first node replacement must complete before a subsequent call can be made. 
 
* To determine whether the node replacement is complete you can check Events using the Amazon ElastiCache console, the AWS CLI, or the ElastiCache API. Look for the following automatic failover related events, listed here in order of occurrance: 

   
  * Replication group message: ``Test Failover API called for node group node-group-id``   
   
  * Cache cluster message: ``Failover from master node primary-node-idto replica node node-idcompleted``   
   
  * Replication group message: ``Failover from master node primary-node-idto replica node node-idcompleted``   
   
  * Cache cluster message: ``Recovering cache nodes node-id``   
   
  * Cache cluster message: ``Finished recovery for cache nodes node-id``   
   

 

For more information see:

 

   
  * `Viewing ElastiCache Events <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/ECEvents.Viewing.html>`_ in the *ElastiCache User Guide*   
   
  * `describe-events <http://docs.aws.amazon.com/AmazonElastiCache/latest/APIReference/API_DescribeEvents.html>`_ in the ElastiCache API Reference 
   

 
 

 

Also see, `Testing Multi-AZ with Automatic Failover <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/AutoFailover.html#auto-failover-test>`_ in the *ElastiCache User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/TestFailover>`_


========
Synopsis
========

::

    test-failover
  --replication-group-id <value>
  --node-group-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--replication-group-id`` (string)


  The name of the replication group (console: cluster) whose automatic failover is being tested by this operation.

  

``--node-group-id`` (string)


  The name of the node group (called shard in the console) in this replication group on which automatic failover is to be tested. You may test automatic failover on up to 5 node groups in any rolling 24-hour period.

  

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

    

    

  

