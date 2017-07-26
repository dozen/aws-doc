[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache create-replication-group:


************************
create-replication-group
************************



===========
Description
===========



The *create-replication-group* action creates a replication group. A replication group is a collection of cache clusters, where one of the cache clusters is a read/write primary and the others are read-only replicas. Writes to the primary are automatically propagated to the replicas.

 

When you create a replication group, you must specify an existing cache cluster that is in the primary role. When the replication group has been successfully created, you can add one or more read replica replicas to it, up to a total of five read replicas.

 

**Note:** This action is valid only for Redis.



========
Synopsis
========

::

    create-replication-group
  --replication-group-id <value>
  --replication-group-description <value>
  [--primary-cluster-id <value>]
  [--automatic-failover-enabled | --no-automatic-failover-enabled]
  [--num-cache-clusters <value>]
  [--preferred-cache-cluster-a-zs <value>]
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

``--replication-group-id`` (string)


  The replication group identifier. This parameter is stored as a lowercase string.

   

  Constraints:

   

   
  * A name must contain from 1 to 20 alphanumeric characters or hyphens.
   
  * The first character must be a letter.
   
  * A name cannot end with a hyphen or contain two consecutive hyphens.
   

  

``--replication-group-description`` (string)


  A user-created description for the replication group.

  

``--primary-cluster-id`` (string)


  The identifier of the cache cluster that will serve as the primary for this replication group. This cache cluster must already exist and have a status of *available* .

   

  This parameter is not required if *NumCacheClusters* is specified.

  

``--automatic-failover-enabled`` | ``--no-automatic-failover-enabled`` (boolean)


  Specifies whether a read-only replica will be automatically promoted to read/write primary if the existing primary fails.

   

  If ``true`` , Multi-AZ is enabled for this replication group. If ``false`` , Multi-AZ is disabled for this replication group.

   

  Default: false

   

  .. note::

    

    ElastiCache Multi-AZ replication groups is not supported on:

     

     
    * Redis versions earlier than 2.8.6.
     
    * T1 and T2 cache node types.
     

     

  

``--num-cache-clusters`` (integer)


  The number of cache clusters this replication group will initially have.

   

  If *Multi-AZ* is ``enabled`` , the value of this parameter must be at least 2.

   

  The maximum permitted value for *NumCacheClusters* is 6 (primary plus 5 replicas). If you need to exceed this limit, please fill out the ElastiCache Limit Increase Request form at `http\://aws.amazon.com/contact-us/elasticache-node-limit-request`_ .

  

``--preferred-cache-cluster-a-zs`` (list)


  A list of EC2 availability zones in which the replication group's cache clusters will be created. The order of the availability zones in the list is not important.

   

  .. note::

    If you are creating your replication group in an Amazon VPC (recommended), you can only locate cache clusters in availability zones associated with the subnets in the selected subnet group. 

    The number of availability zones listed must equal the value of *NumCacheClusters* .

    

   

  Default: system chosen availability zones.

   

  Example: One Redis cache cluster in each of three availability zones. PreferredAvailabilityZones.member.1=us-west-2a PreferredAvailabilityZones.member.2=us-west-2c PreferredAvailabilityZones.member.3=us-west-2c

  



Syntax::

  "string" "string" ...



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


  The name of the cache engine to be used for the cache clusters in this replication group.

   

  Default: redis

  

``--engine-version`` (string)


  The version number of the cache engine to be used for the cache clusters in this replication group. To view the supported cache engine versions, use the *describe-cache-engine-versions* action.

  

``--cache-parameter-group-name`` (string)


  The name of the parameter group to associate with this replication group. If this argument is omitted, the default cache parameter group for the specified engine is used.

  

``--cache-subnet-group-name`` (string)


  The name of the cache subnet group to be used for the replication group.

  

``--cache-security-group-names`` (list)


  A list of cache security group names to associate with this replication group.

  



Syntax::

  "string" "string" ...



``--security-group-ids`` (list)


  One or more Amazon VPC security groups associated with this replication group.

   

  Use this parameter only when you are creating a replication group in an Amazon Virtual Private Cloud (VPC).

  



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


  The port number on which each member of the replication group will accept connections.

  

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
       

       

    

    

  



.. _http\://aws.amazon.com/contact-us/elasticache-node-limit-request: http://aws.amazon.com/contact-us/elasticache-node-limit-request
.. _Cache Node Type-Specific Parameters for Memcached: http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheParameterGroups.Memcached.html#CacheParameterGroups.Memcached.NodeSpecific
.. _Amazon ElastiCache Product Features and Details: http://aws.amazon.com/elasticache/details
.. _Cache Node Type-Specific Parameters for Redis: http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheParameterGroups.Redis.html#CacheParameterGroups.Redis.NodeSpecific
