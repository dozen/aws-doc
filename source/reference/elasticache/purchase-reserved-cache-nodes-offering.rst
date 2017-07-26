[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache purchase-reserved-cache-nodes-offering:


**************************************
purchase-reserved-cache-nodes-offering
**************************************



===========
Description
===========



The *purchase-reserved-cache-nodes-offering* action allows you to purchase a reserved cache node offering.



========
Synopsis
========

::

    purchase-reserved-cache-nodes-offering
  --reserved-cache-nodes-offering-id <value>
  [--reserved-cache-node-id <value>]
  [--cache-node-count <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--reserved-cache-nodes-offering-id`` (string)


  The ID of the reserved cache node offering to purchase.

   

  Example: 438012d3-4052-4cc7-b2e3-8d3372e0e706

  

``--reserved-cache-node-id`` (string)


  A customer-specified identifier to track this reservation.

   

  Example: myreservationID

  

``--cache-node-count`` (integer)


  The number of cache node instances to reserve.

   

  Default: ``1`` 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ReservedCacheNode -> (structure)

  

  Represents the output of a *purchase-reserved-cache-nodes-offering* action.

  

  ReservedCacheNodeId -> (string)

    

    The unique identifier for the reservation.

    

    

  ReservedCacheNodesOfferingId -> (string)

    

    The offering identifier.

    

    

  CacheNodeType -> (string)

    

    The cache node type for the reserved cache nodes.

     

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

    

    

  StartTime -> (timestamp)

    

    The time the reservation started.

    

    

  Duration -> (integer)

    

    The duration of the reservation in seconds.

    

    

  FixedPrice -> (double)

    

    The fixed price charged for this reserved cache node.

    

    

  UsagePrice -> (double)

    

    The hourly price charged for this reserved cache node.

    

    

  CacheNodeCount -> (integer)

    

    The number of cache nodes that have been reserved.

    

    

  ProductDescription -> (string)

    

    The description of the reserved cache node.

    

    

  OfferingType -> (string)

    

    The offering type of this reserved cache node.

    

    

  State -> (string)

    

    The state of the reserved cache node.

    

    

  RecurringCharges -> (list)

    

    The recurring price charged to run this reserved cache node.

    

    (structure)

      

      Contains the specific price and frequency of a recurring charges for a reserved cache node, or for a reserved cache node offering.

      

      RecurringChargeAmount -> (double)

        

        The monetary amount of the recurring charge.

        

        

      RecurringChargeFrequency -> (string)

        

        The frequency of the recurring charge.

        

        

      

    

  



.. _Cache Node Type-Specific Parameters for Memcached: http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheParameterGroups.Memcached.html#CacheParameterGroups.Memcached.NodeSpecific
.. _Amazon ElastiCache Product Features and Details: http://aws.amazon.com/elasticache/details
.. _Cache Node Type-Specific Parameters for Redis: http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheParameterGroups.Redis.html#CacheParameterGroups.Redis.NodeSpecific
