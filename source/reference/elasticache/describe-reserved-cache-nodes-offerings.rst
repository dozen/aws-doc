[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache describe-reserved-cache-nodes-offerings:


***************************************
describe-reserved-cache-nodes-offerings
***************************************



===========
Description
===========



The *describe-reserved-cache-nodes-offerings* action lists available reserved cache node offerings.



``describe-reserved-cache-nodes-offerings`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ReservedCacheNodesOfferings``


========
Synopsis
========

::

    describe-reserved-cache-nodes-offerings
  [--reserved-cache-nodes-offering-id <value>]
  [--cache-node-type <value>]
  [--duration <value>]
  [--product-description <value>]
  [--offering-type <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--reserved-cache-nodes-offering-id`` (string)


  The offering identifier filter value. Use this parameter to show only the available offering that matches the specified reservation identifier.

   

  Example: ``438012d3-4052-4cc7-b2e3-8d3372e0e706`` 

  

``--cache-node-type`` (string)


  The cache node type filter value. Use this parameter to show only the available offerings matching the specified cache node type.

   

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

  

``--duration`` (string)


  Duration filter value, specified in years or seconds. Use this parameter to show only reservations for a given duration.

   

  Valid Values: ``1 | 3 | 31536000 | 94608000`` 

  

``--product-description`` (string)


  The product description filter value. Use this parameter to show only the available offerings matching the specified product description.

  

``--offering-type`` (string)


  The offering type filter value. Use this parameter to show only the available offerings matching the specified offering type.

   

  Valid Values: ``"Light Utilization"|"Medium Utilization"|"Heavy Utilization"`` 

  

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

  

  Provides an identifier to allow retrieval of paginated results.

  

  

ReservedCacheNodesOfferings -> (list)

  

  A list of reserved cache node offerings. Each element in the list contains detailed information about one offering.

  

  (structure)

    

    Describes all of the attributes of a reserved cache node offering.

    

    ReservedCacheNodesOfferingId -> (string)

      

      A unique identifier for the reserved cache node offering.

      

      

    CacheNodeType -> (string)

      

      The cache node type for the reserved cache node.

       

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

      

      

    Duration -> (integer)

      

      The duration of the offering. in seconds.

      

      

    FixedPrice -> (double)

      

      The fixed price charged for this offering.

      

      

    UsagePrice -> (double)

      

      The hourly price charged for this offering.

      

      

    ProductDescription -> (string)

      

      The cache engine used by the offering.

      

      

    OfferingType -> (string)

      

      The offering type.

      

      

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
