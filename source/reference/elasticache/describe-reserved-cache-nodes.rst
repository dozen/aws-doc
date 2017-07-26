[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache describe-reserved-cache-nodes:


*****************************
describe-reserved-cache-nodes
*****************************



===========
Description
===========



Returns information about reserved cache nodes for this account, or about a specified reserved cache node.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/DescribeReservedCacheNodes>`_


``describe-reserved-cache-nodes`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ReservedCacheNodes``


========
Synopsis
========

::

    describe-reserved-cache-nodes
  [--reserved-cache-node-id <value>]
  [--reserved-cache-nodes-offering-id <value>]
  [--cache-node-type <value>]
  [--duration <value>]
  [--product-description <value>]
  [--offering-type <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--reserved-cache-node-id`` (string)


  The reserved cache node identifier filter value. Use this parameter to show only the reservation that matches the specified reservation ID.

  

``--reserved-cache-nodes-offering-id`` (string)


  The offering identifier filter value. Use this parameter to show only purchased reservations matching the specified offering identifier.

  

``--cache-node-type`` (string)


  The cache node type filter value. Use this parameter to show only those reservations matching the specified cache node type.

   

  Valid node types are as follows:

   

   
  * General purpose: 

     
    * Current generation: ``cache.t2.micro`` , ``cache.t2.small`` , ``cache.t2.medium`` , ``cache.m3.medium`` , ``cache.m3.large`` , ``cache.m3.xlarge`` , ``cache.m3.2xlarge`` , ``cache.m4.large`` , ``cache.m4.xlarge`` , ``cache.m4.2xlarge`` , ``cache.m4.4xlarge`` , ``cache.m4.10xlarge``   
     
    * Previous generation: ``cache.t1.micro`` , ``cache.m1.small`` , ``cache.m1.medium`` , ``cache.m1.large`` , ``cache.m1.xlarge``   
     

   
   
  * Compute optimized: ``cache.c1.xlarge``   
   
  * Memory optimized: 

     
    * Current generation: ``cache.r3.large`` , ``cache.r3.xlarge`` , ``cache.r3.2xlarge`` , ``cache.r3.4xlarge`` , ``cache.r3.8xlarge``   
     
    * Previous generation: ``cache.m2.xlarge`` , ``cache.m2.2xlarge`` , ``cache.m2.4xlarge``   
     

   
   

   

   **Notes:**  

   

   
  * All T2 instances are created in an Amazon Virtual Private Cloud (Amazon VPC). 
   
  * Redis backup/restore is not supported for Redis (cluster mode disabled) T1 and T2 instances. Backup/restore is supported on Redis (cluster mode enabled) T2 instances. 
   
  * Redis Append-only files (AOF) functionality is not supported for T1 or T2 instances. 
   

   

  For a complete listing of node types and specifications, see `Amazon ElastiCache Product Features and Details <http://aws.amazon.com/elasticache/details>`_ and either `Cache Node Type-Specific Parameters for Memcached <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheParameterGroups.Memcached.html#ParameterGroups.Memcached.NodeSpecific>`_ or `Cache Node Type-Specific Parameters for Redis <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheParameterGroups.Redis.html#ParameterGroups.Redis.NodeSpecific>`_ .

  

``--duration`` (string)


  The duration filter value, specified in years or seconds. Use this parameter to show only reservations for this duration.

   

  Valid Values: ``1 | 3 | 31536000 | 94608000``  

  

``--product-description`` (string)


  The product description filter value. Use this parameter to show only those reservations matching the specified product description.

  

``--offering-type`` (string)


  The offering type filter value. Use this parameter to show only the available offerings matching the specified offering type.

   

  Valid values: ``"Light Utilization"|"Medium Utilization"|"Heavy Utilization"``  

  

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

  

  

ReservedCacheNodes -> (list)

  

  A list of reserved cache nodes. Each element in the list contains detailed information about one node.

  

  (structure)

    

    Represents the output of a ``purchase-reserved-cache-nodes-offering`` operation.

    

    ReservedCacheNodeId -> (string)

      

      The unique identifier for the reservation.

      

      

    ReservedCacheNodesOfferingId -> (string)

      

      The offering identifier.

      

      

    CacheNodeType -> (string)

      

      The cache node type for the reserved cache nodes.

       

      Valid node types are as follows:

       

       
      * General purpose: 

         
        * Current generation: ``cache.t2.micro`` , ``cache.t2.small`` , ``cache.t2.medium`` , ``cache.m3.medium`` , ``cache.m3.large`` , ``cache.m3.xlarge`` , ``cache.m3.2xlarge`` , ``cache.m4.large`` , ``cache.m4.xlarge`` , ``cache.m4.2xlarge`` , ``cache.m4.4xlarge`` , ``cache.m4.10xlarge``   
         
        * Previous generation: ``cache.t1.micro`` , ``cache.m1.small`` , ``cache.m1.medium`` , ``cache.m1.large`` , ``cache.m1.xlarge``   
         

       
       
      * Compute optimized: ``cache.c1.xlarge``   
       
      * Memory optimized: 

         
        * Current generation: ``cache.r3.large`` , ``cache.r3.xlarge`` , ``cache.r3.2xlarge`` , ``cache.r3.4xlarge`` , ``cache.r3.8xlarge``   
         
        * Previous generation: ``cache.m2.xlarge`` , ``cache.m2.2xlarge`` , ``cache.m2.4xlarge``   
         

       
       

       

       **Notes:**  

       

       
      * All T2 instances are created in an Amazon Virtual Private Cloud (Amazon VPC). 
       
      * Redis backup/restore is not supported for Redis (cluster mode disabled) T1 and T2 instances. Backup/restore is supported on Redis (cluster mode enabled) T2 instances. 
       
      * Redis Append-only files (AOF) functionality is not supported for T1 or T2 instances. 
       

       

      For a complete listing of node types and specifications, see `Amazon ElastiCache Product Features and Details <http://aws.amazon.com/elasticache/details>`_ and either `Cache Node Type-Specific Parameters for Memcached <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheParameterGroups.Memcached.html#ParameterGroups.Memcached.NodeSpecific>`_ or `Cache Node Type-Specific Parameters for Redis <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/CacheParameterGroups.Redis.html#ParameterGroups.Redis.NodeSpecific>`_ .

      

      

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

          

          

        

      

    

  

