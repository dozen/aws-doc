[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache describe-replication-groups:


***************************
describe-replication-groups
***************************



===========
Description
===========



The *describe-replication-groups* action returns information about a particular replication group. If no identifier is specified, *describe-replication-groups* returns information about all replication groups.



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
  [--generate-cli-skeleton]




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

  

  

ReplicationGroups -> (list)

  

  A list of replication groups. Each item in the list contains detailed information about one replication group.

  

  (structure)

    

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
         

         

      

      

    

  

