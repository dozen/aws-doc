[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache delete-replication-group:


************************
delete-replication-group
************************



===========
Description
===========



The *delete-replication-group* action deletes an existing replication group. By default, this action deletes the entire replication group, including the primary cluster and all of the read replicas. You can optionally delete only the read replicas, while retaining the primary cluster.

 

When you receive a successful response from this action, Amazon ElastiCache immediately begins deleting the selected resources; you cannot cancel or revert this action.



========
Synopsis
========

::

    delete-replication-group
  --replication-group-id <value>
  [--retain-primary-cluster | --no-retain-primary-cluster]
  [--final-snapshot-identifier <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--replication-group-id`` (string)


  The identifier for the cluster to be deleted. This parameter is not case sensitive.

  

``--retain-primary-cluster`` | ``--no-retain-primary-cluster`` (boolean)


  If set to *true* , all of the read replicas will be deleted, but the primary node will be retained.

  

``--final-snapshot-identifier`` (string)


  The name of a final node group snapshot. ElastiCache creates the snapshot from the primary node in the cluster, rather than one of the replicas; this is to ensure that it captures the freshest data. After the final snapshot is taken, the cluster is immediately deleted.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ReplicationGroup -> (structure)

  

  Contains all of the attributes of a specific replication group.

  

  ReplicationGroupId -> (string)

    

    The identifier for the replication group.

    

    

  Description -> (string)

    

    The description of the replication group.

    

    

  Status -> (string)

    

    The current state of this replication group - *creating* , *available* , etc.

    

    

  PendingModifiedValues -> (structure)

    

    A group of settings to be applied to the replication group, either immediately or during the next maintenance window.

    

    PrimaryClusterId -> (string)

      

      The primary cluster ID which will be applied immediately (if ``--apply-immediately`` was specified), or during the next maintenance window.

      

      

    AutomaticFailoverStatus -> (string)

      

      Indicates the status of Multi-AZ for this replication group.

       

      .. note::

        

        ElastiCache Multi-AZ replication groups are not supported on:

         

         
        * Redis versions earlier than 2.8.6.
         
        * T1 and T2 cache node types.
         

         

      

      

    

  MemberClusters -> (list)

    

    The names of all the cache clusters that are part of this replication group.

    

    (string)

      

      

    

  NodeGroups -> (list)

    

    A single element list with information about the nodes in the replication group.

    

    (structure)

      

      Represents a collection of cache nodes in a replication group.

      

      NodeGroupId -> (string)

        

        The identifier for the node group. A replication group contains only one node group; therefore, the node group ID is 0001.

        

        

      Status -> (string)

        

        The current state of this replication group - *creating* , *available* , etc.

        

        

      PrimaryEndpoint -> (structure)

        

        Represents the information required for client programs to connect to a cache node.

        

        Address -> (string)

          

          The DNS hostname of the cache node.

          

          

        Port -> (integer)

          

          The port number that the cache engine is listening on.

          

          

        

      NodeGroupMembers -> (list)

        

        A list containing information about individual nodes within the node group.

        

        (structure)

          

          Represents a single node within a node group.

          

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

            

            The role that is currently assigned to the node - *primary* or *replica* .

            

            

          

        

      

    

  SnapshottingClusterId -> (string)

    

    The cache cluster ID that is used as the daily snapshot source for the replication group.

    

    

  AutomaticFailover -> (string)

    

    Indicates the status of Multi-AZ for this replication group.

     

    .. note::

      

      ElastiCache Multi-AZ replication groups are not supported on:

       

       
      * Redis versions earlier than 2.8.6.
       
      * T1 and T2 cache node types.
       

       

    

    

  

