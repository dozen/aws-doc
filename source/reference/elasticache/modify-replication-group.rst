[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache modify-replication-group:


************************
modify-replication-group
************************



===========
Description
===========



The *modify-replication-group* action modifies the settings for a replication group.



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
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--replication-group-id`` (string)


  The identifier of the replication group to modify.

  

``--replication-group-description`` (string)


  A description for the replication group. Maximum length is 255 characters.

  

``--primary-cluster-id`` (string)


  If this parameter is specified, ElastiCache will promote each of the cache clusters in the specified replication group to the primary role. The nodes of all other cache clusters in the replication group will be read replicas.

  

``--snapshotting-cluster-id`` (string)


  The cache cluster ID that will be used as the daily snapshot source for the replication group.

  

``--automatic-failover-enabled`` | ``--no-automatic-failover-enabled`` (boolean)


  Whether a read replica will be automatically promoted to read/write primary if the existing primary encounters a failure.

   

  Valid values: ``true`` | ``false`` 

   

  .. note::

    

    ElastiCache Multi-AZ replication groups are not supported on:

     

     
    * Redis versions earlier than 2.8.6.
     
    * T1 and T2 cache node types.
     

     

  

``--cache-security-group-names`` (list)


  A list of cache security group names to authorize for the clusters in this replication group. This change is asynchronously applied as soon as possible.

   

  This parameter can be used only with replication group containing cache clusters running outside of an Amazon Virtual Private Cloud (VPC).

   

  Constraints: Must contain no more than 255 alphanumeric characters. Must not be "Default".

  



Syntax::

  "string" "string" ...



``--security-group-ids`` (list)


  Specifies the VPC Security Groups associated with the cache clusters in the replication group.

   

  This parameter can be used only with replication group containing cache clusters running in an Amazon Virtual Private Cloud (VPC).

  



Syntax::

  "string" "string" ...



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

  

``--notification-topic-arn`` (string)


  The Amazon Resource Name (ARN) of the Amazon SNS topic to which notifications will be sent.

   

  .. note::

    The Amazon SNS topic owner must be same as the replication group owner. 

  

``--cache-parameter-group-name`` (string)


  The name of the cache parameter group to apply to all of the clusters in this replication group. This change is asynchronously applied as soon as possible for parameters when the *ApplyImmediately* parameter is specified as *true* for this request.

  

``--notification-topic-status`` (string)


  The status of the Amazon SNS notification topic for the replication group. Notifications are sent only if the status is *active* .

   

  Valid values: ``active`` | ``inactive`` 

  

``--apply-immediately`` | ``--no-apply-immediately`` (boolean)


  If ``true`` , this parameter causes the modifications in this request and any pending modifications to be applied, asynchronously and as soon as possible, regardless of the *PreferredMaintenanceWindow* setting for the replication group.

   

  If ``false`` , then changes to the nodes in the replication group are applied on the next maintenance reboot, or the next failure reboot, whichever occurs first.

   

  Valid values: ``true`` | ``false`` 

   

  Default: ``false`` 

  

``--engine-version`` (string)


  The upgraded version of the cache engine to be run on the cache clusters in the replication group.

  

``--auto-minor-version-upgrade`` | ``--no-auto-minor-version-upgrade`` (boolean)


  This parameter is currently disabled.

  

``--snapshot-retention-limit`` (integer)


  The number of days for which ElastiCache will retain automatic node group snapshots before deleting them. For example, if you set *SnapshotRetentionLimit* to 5, then a snapshot that was taken today will be retained for 5 days before being deleted.

   

  **Important** If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.

  

``--snapshot-window`` (string)


  The daily time range (in UTC) during which ElastiCache will begin taking a daily snapshot of the node group specified by *SnapshottingClusterId* .

   

  Example: ``05:00-09:00`` 

   

  If you do not specify this parameter, then ElastiCache will automatically choose an appropriate time range.

  

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
       

       

    

    

  

