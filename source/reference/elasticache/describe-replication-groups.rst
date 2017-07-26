[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache describe-replication-groups:


***************************
describe-replication-groups
***************************



===========
Description
===========



Returns information about a particular replication group. If no identifier is specified, ``describe-replication-groups`` returns information about all replication groups.

 

.. note::

   

  This operation is valid for Redis only.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/DescribeReplicationGroups>`_


``describe-replication-groups`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ReplicationGroups``


========
Synopsis
========

::

    describe-replication-groups
  [--replication-group-id <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--replication-group-id`` (string)


  The identifier for the replication group to be described. This parameter is not case sensitive.

   

  If you do not specify this parameter, information about all replication groups is returned.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Marker -> (string)

  

  Provides an identifier to allow retrieval of paginated results.

  

  

ReplicationGroups -> (list)

  

  A list of replication groups. Each item in the list contains detailed information about one replication group.

  

  (structure)

    

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

      

      

    

  

